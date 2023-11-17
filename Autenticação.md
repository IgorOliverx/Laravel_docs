## Facade `Auth` no Laravel

### Finalidade Principal:
- O Facade `Auth` é uma classe poderosa no Laravel para autenticação, recuperação e gerenciamento de informações do usuário.

### Funcionalidades:
- **Verificação de Status:** Permite verificar o status da autenticação.
- **Quantidade de Usuários:** Facilita a contagem ou obtenção de informações sobre usuários autenticados.
- **Gerenciamento de Sessões:** Facilita o controle sobre quem está logado e a manipulação das sessões.
- **Acesso a Endpoints Específicos:** Facilita a restrição ou permitir acesso a endpoints específicos usando middlewares.

### Controladores Relacionados:
- **AuthController:** Responsável por gerenciar a lógica do usuário, incluindo a autenticação.
- **PasswordController:** Lida com a lógica de resete de senhas dos usuários.

### Uso de Métodos:

### Recuperar Informações de Usuário:
- `Auth::user()`: Retorna uma instância do usuário autenticado.
- Exemplo de uso em um controlador:
  ```php
  if ($request->user()) {
    // Retorna uma instância do usuário autenticado
  }
  ```


### Verificar Autenticação do Usuário Atual:
- `Auth::check()`: Verifica se o usuário está autenticado.
- Exemplo:
  ```php
  if(Auth::check()){
    // Faça o que for necessário para um usuário autenticado
  }
  ```


### Restringir Rotas para Usuários Autenticados:
- Usando middleware:
  ```php
  Route::middleware('auth')->group(function(){
    Route::get('/rota', [ClassController::class, 'metodo']);
  });
  ```
  Lembre-se de adicionar isso ao middleware do kernel.
  ```
  protected $routeMiddleware = [
    'auth' => Authenticate::class,
  ];


### Autenticação Manual de Usuários:
- Exemplo simples:
  ```php
  public function autenticar()
  {
    if (Auth::attempt(['email' => $email, 'password' => $password])) {
      // Autenticado com sucesso
      return redirect()->intended('dashboard');
    }
  }
  ```
  - O método `attempt` busca o usuário no banco de dados usando o email e compara a senha fornecida.
  - O método `intended` redireciona o usuário de volta para a URL que estava acessando antes da autenticação.
 

  
### Deslogar Usuários:
- `Auth::logout()`: Limpa a sessão e todos os cookies do usuário, efetivamente fazendo logout.



### Registro de Novos Usuários (em versões mais recentes):
```php
use Illuminate\Support\Facades\Auth;

$user = Auth::createUser([
    'name' => 'Nome do Novo Usuário',
    'email' => 'novoemail@example.com',
    'password' => bcrypt('senha123'),
]);
```

### Redirecionamento e Manipulação de Sessões:
```php
// Verificar se o usuário está autenticado
if (Auth::check()) {
    // Lógica para usuários autenticados
}

// Redirecionar usuário convidado (guest) para página de login
if (Auth::guest()) {
    return redirect()->route('login');
}

// Autenticar usuário com um ID específico
Auth::loginUsingId(1);

// Autenticar usuário manualmente
$user = User::find(1);
Auth::login($user);

// Redirecionamento após autenticação bem-sucedida
if (Auth::viaRemember()) {
    // Usuário está autenticado por "lembrar-me"
}
```

### Personalização e Extensibilidade:
```php
// Configurações de autenticação personalizadas no arquivo config/auth.php
'passwords' => [
    'users' => [
        'provider' => 'users',
        'table' => 'password_resets',
        'expire' => 60,
    ],
],

// Eventos de autenticação no Laravel para ações personalizadas
Event::listen('Illuminate\Auth\Events\Login', function ($user, $remember) {
    // Ações após o login do usuário
});
```

### Segurança:
```php
// Proteção contra ataques de força bruta
// O Laravel possui medidas integradas para bloquear contas após tentativas malsucedidas de login

// Token CSRF (Cross-Site Request Forgery) é automaticamente gerado no Laravel para proteger contra ataques CSRF
// Não requer código adicional para funcionar
```

### Customização e Extensões:
```php
// Aqui você pode personalizar o redirecionamento após a autenticação bem-sucedida
protected function authenticated(Request $request, $user) {
    if ($user->isAdmin()) {
        return redirect()->route('admin.dashboard');
    }
    return redirect('/home');
}

// Pacotes de extensão para autenticação social, como Socialite para login via Facebook, Google, etc. API DE LOGIN
// Instalação via Composer: composer require laravel/socialite
```


### Observação:
O Facade `Auth` oferece uma gama de funcionalidades para gerenciar a autenticação e as sessões dos usuários no Laravel. É uma ferramenta poderosa que facilita o desenvolvimento de sistemas de autenticação robustos e seguros.
