
# Manipulação de JSON no Laravel

O Laravel oferece recursos integrados poderosos para manipular dados em formato JSON, seja preenchendo o banco de dados a partir de arquivos JSON ou processando respostas recebidas do frontend.

## 1. Preenchendo o Banco de Dados com Arquivos JSON

### a. Seeding com Arquivos JSON

Você pode usar o recurso de *seeding* do Laravel para preencher o banco de dados com dados provenientes de arquivos JSON. Crie arquivos de seed com os dados e use os *Seeders* do Laravel para importar esses dados.

Exemplo:

1. Crie um arquivo `users.json` com dados de usuários:

```json
[
    {
        "name": "John Doe",
        "email": "john@example.com",
        "password": "hashed_password"
    },
    {
        "name": "Jane Doe",
        "email": "jane@example.com",
        "password": "hashed_password"
    }
]
```

2. Crie um *seeder* (`UserSeeder`) para importar os dados do arquivo JSON:

```php
public function run()
{
    $users = json_decode(file_get_contents(database_path('seeders/users.json')), true);

    foreach ($users as $user) {
        User::create([
            'name' => $user['name'],
            'email' => $user['email'],
            'password' => Hash::make($user['password'])
        ]);
    }
}
```

### b. Leitura e Processamento de Arquivos JSON

Você também pode ler e processar arquivos JSON diretamente no Laravel para manipulação adicional dos dados.

Exemplo:

```php
$jsonData = file_get_contents('caminho/do/arquivo.json');
$data = json_decode($jsonData, true);

// Manipular e utilizar os dados
foreach ($data as $item) {
    // Faça algo com cada item do JSON
}
```
Claro, a manipulação de dados JSON provenientes do frontend para o backend é uma parte fundamental em muitas aplicações modernas. No Laravel, o recebimento e processamento desses dados são feitos através do objeto `Request`. Vou expandir mais essa seção para cobrir diversos cenários:




## 2. Recebendo e Decodificando Requisições JSON

#### a. Enviando dados JSON para o Backend

Ao enviar dados do frontend para o backend, você pode usar `axios`(JS), `fetch`(React), `HtpClient`(Angular) ou outras bibliotecas para fazer requisições HTTP. Certifique-se de enviar os dados no formato JSON.

Exemplo usando `axios`:

```javascript
// Enviando dados para o backend
axios.post('/api/data', {
    key: 'value',
    // Outros dados
})
.then(response => {
    // Tratar a resposta, se necessário
})
.catch(error => {
    // Tratar erros, se necessário
});
```

#### b. Recebendo e Decodificando no Laravel


Exemplo no controller do Laravel:

```php
use Illuminate\Http\Request;

public function receiveData(Request $request)
{
    $data = $request->json()->all();

    // Processar os dados recebidos
    // Exemplo de manipulação: $data['key']

    return response()->json(['message' => 'Data received successfully']);
}
```

### 2. Validação de Dados JSON

#### a. Usando Validação de Request

O Laravel fornece uma maneira fácil de validar dados provenientes de requisições, incluindo dados JSON.

Exemplo:

```php
use Illuminate\Http\Request;

public function receiveAndValidateData(Request $request)
{
    $validatedData = $request->validate([
        'key' => 'required|string|max:255',
        // Outros campos e regras de validação
    ]);

    // Se chegar até aqui, os dados são válidos
    // Manipular $validatedData
}
```

### 3. Respostas JSON do Backend para o Frontend

Ao enviar respostas do backend para o frontend, é comum retornar dados no formato JSON.

Exemplo:

```php
public function sendDataBack()
{
    $data = ['key' => 'value'];

    return response()->json($data);
}
```
---

# Exemplo real
---
Formulário de cadastro feito no angular e processado no laravel

## Front-End

Passo 1: **Criando o componente do formulário de cadastro**

Crie um componente no Angular para o formulário de cadastro. Este exemplo supõe que você já configurou o ambiente Angular.

```typescript
// registration-form.component.ts

import { Component } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Component({
  selector: 'app-registration-form',
  templateUrl: './registration-form.component.html',
  styleUrls: ['./registration-form.component.css']
})
export class RegistrationFormComponent {
  name: string = '';
  email: string = '';
  password: string = '';

  constructor(private http: HttpClient) {}

  onSubmit(): void {
    const formData = {
      name: this.name,
      email: this.email,
      password: this.password
    };

    this.http.post<any>('/api/register', formData)
      .subscribe(
        response => {
          console.log(response); // Manipule a resposta do servidor aqui, se necessário
        },
        error => {
          console.error(error);
        }
      );
  }
}
```

Passo 2: **Criando o template HTML do formulário**

```html
<!-- registration-form.component.html -->
<form (ngSubmit)="onSubmit()">
  <input type="text" [(ngModel)]="name" name="name" placeholder="Nome"><br>
  <input type="email" [(ngModel)]="email" name="email" placeholder="Email"><br>
  <input type="password" [(ngModel)]="password" name="password" placeholder="Senha"><br>
  <button type="submit">Cadastrar</button>
</form>
```

Passo 3: **Configuração do módulo do Angular**

Certifique-se de importar e configurar o `HttpClientModule` no seu módulo principal ou no módulo que está utilizando o componente do formulário.

```typescript
// app.module.ts

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { HttpClientModule } from '@angular/common/http';

import { AppComponent } from './app.component';
import { RegistrationFormComponent } from './registration-form/registration-form.component';

@NgModule({
  declarations: [
    AppComponent,
    RegistrationFormComponent
  ],
  imports: [
    BrowserModule,
    HttpClientModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## Back-end

Passo 1: **Recebendo e processando a requisição no Laravel**

Vamos criar uma rota para receber os dados do formulário, processá-los e armazená-los no banco de dados.

```php
// routes/api.php

use App\Http\Controllers\UserController;

Route::post('/register', [UserController::class, 'register']);
```

Passo 2: **Controller para manipular a requisição**

Aqui, vamos criar o controller responsável por processar os dados recebidos e armazená-los no banco de dados.

Também, você precisará adicionar a exceção 'api/register' ao middleware VerifyCsrfToken no arquivo 'app/Http/Middleware/VerifyCsrfToken.php':

// app/Http/Middleware/VerifyCsrfToken.php

protected $except = [
    'api/register',
];

```php
// app/Http/Controllers/UserController.php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\Models\User;

class UserController extends Controller
{

    public function __construct()
  {//Esse construtor encerrará o token csrf. Isso impedirá problemas com a ORM(O front foi feito em angular, ele que cuidará de sql injection)
      $this->middleware(['auth:api', 'verified'])->except(['register']);
  }

    public function register(Request $request)
    {
        // Validar os dados recebidos
        $validatedData = $request->validate([
            'name' => 'required|string|max:255',
            'email' => 'required|email|unique:users',
            'password' => 'required|min:6',
        ]);
          $validatedData['password'] = bcrypt($validatedData['password']);

        // Criar um novo usuário com os dados recebidos
        $user = User::create($validatedData);

        return response()->json(['message' => 'Usuário cadastrado com sucesso', 'user' => $user]);
    }
}
```

Passo 3: **Model para interação com o banco de dados**

Este é um modelo de exemplo para a tabela `users`.

```php
// app/Models/User.php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class User extends Model
{
    use HasFactory;

    protected $table = 'usuario';

    protected $fillable = [
        'name',
        'email',
        'password',
    ];
    protected $hidden = [
          'password'
    ];
}
```


