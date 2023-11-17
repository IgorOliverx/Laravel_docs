# Como manipular banco de dados sem utilizar a migrate do laravel.(APENAS ORM)

- [Definindo um model](Usando-Modelos-com-Dados-Preexistentes-no-Banco-de-Dados)
- [Interagindo com dados](Interagindo-com-os-Dados)
- - [Buscando registros](Interagindo-com-os-Dados)
  - - [Buscando registros por id](Interagindo-com-os-Dados)
- [Deletando registros](Deletar-um-Registro)


### Usando Modelos com Dados Preexistentes no Banco de Dados

#### 1. Definindo o Model

- **Defina o Model com o Nome da Tabela:**
  ```php
  class SeuModel extends Model {
      protected $table = 'nome_da_sua_tabela';
  }
  ```

- **Especifique Atributos Fillable (Preenchíveis), se necessário:**
  ```php
  class SeuModel extends Model {
      protected $fillable = ['campo1', 'campo2', 'campo3'];
  }
  ```

#### 2. Interagindo com os Dados

- **Buscando Registros:**
  ```php
  $registros = SeuModel::all(); // Recupera todos os registros da tabela
  ```

- **Buscar um Registro por ID:**
  ```php
  $registro = SeuModel::find($id); // Recupera um registro pelo ID
  ```

- **Buscar Registros com Condições:**
  ```php
  $registros = SeuModel::where('campo', 'valor')->get(); // Busca com condições
  ```

- **Criar/Atualizar Registros:**
  ```php
  $novoRegistro = SeuModel::create([
      'campo1' => 'Valor 1',
      'campo2' => 'Valor 2',
      // ...
  ]);
  
  $registroExistente = SeuModel::find($id);
  $registroExistente->campo1 = 'Novo valor';
  $registroExistente->save();
  ```

- **Deletar um Registro:**
  ```php
  $registroParaDeletar = SeuModel::find($id);
  $registroParaDeletar->delete();
  ```

Usando a Eloquent ORM dessa maneira, você pode interagir com os dados existentes no seu banco de dados sem a necessidade de definir explicitamente a estrutura do banco por meio de migrations. A Eloquent permite que você trabalhe com os dados conforme necessário, usando os modelos para representar as tabelas existentes. Isso facilita a manipulação dos dados e a construção de consultas de forma mais organizada e amigável ao código.

ISSO É NECESSÁRIO EM MEU CASO. EU APENAS FAÇO O BACK-END, NORMALMENTE, TODO O BANCO DE DADOS VEM ESTRUTURADO E ROBUSTO EM UM SERVIDOR PRONTO PARA EU SOMENTE MANIPULAR AS LÓGICAS NECESSÁRIAS
