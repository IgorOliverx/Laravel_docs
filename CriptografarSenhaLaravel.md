# Criptografia de senhas no Laravel

A criptografia de senhas é uma prática fundamental para proteger as informações dos usuários. No Laravel, o framework oferece recursos embutidos para facilitar o processo de criptografia e armazenamento seguro de senhas. O método recomendado para isso é usar a função `Hash::make()`.

### Recuperar senhas do banco de dados e criptografar para o padrão laravel
```php
use Illuminate\Support\Facades\DB;
use Illuminate\Support\Facades\Hash;

// Recuperando senhas do banco de dados(defina a tabela no model USER)
$users = DB::table('users')->select('id', 'password')->get();

foreach ($users as $user) {
    // Verificando se a senha precisa ser recriptografada (se não estiver já usando o formato do Laravel)
    if (!Hash::needsRehash($user->password)) {
        // Criptografando a senha no formato do Laravel
        $hashedPassword = Hash::make($user->password);

        // Atualizando a senha no banco de dados
        DB::table('users')->where('id', $user->id)->update(['password' => $hashedPassword]);
    }
}

echo "Senhas recriptografadas com sucesso!";
```
O uso do `Hash::make()` do Laravel garante que as senhas sejam criptografadas de acordo com as práticas de segurança recomendadas pela comunidade Laravel, usando algoritmos seguros de hash de senha. Isso garante uma maior proteção das credenciais dos usuários.

