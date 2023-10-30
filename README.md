# Spring Security
Spring Security é uma estrutura de autenticação e controle de acesso poderosa e altamente personalizável. É o padrão para proteger aplicativos baseados em Spring.

## JWT
JWT (JSON Web Token) é um padrão da indústria (RFC-7519) que define como transmitir e armazenar objetos JSON de forma compacta e segura entre diferentes aplicações. O JWT pode ser assinado usando um segredo (com o algoritmo HMAC) ou um par de chaves pública / privada usando RSA ou ECDSA.

<img src="Capturar.PNG" alt="Project logo">

## UserDetails
A interface UserDetails contém informações sobre o usuário, como nome de usuário, senha, autoridades e detalhes da conta.

O Spring Security possui uma classe User que implementa a interface UserDetails. Como uma alternativa de criar sua propria classe, você pode usar a classe User do Spring Security.

### Interface UserDetails
```java
public interface UserDetails extends Serializable {
    Collection<? extends GrantedAuthority> getAuthorities();
    String getPassword();
    String getUsername();
    boolean isAccountNonExpired();
    boolean isAccountNonLocked();
    boolean isCredentialsNonExpired();
    boolean isEnabled();
}
```    

## Novas informações
Aqui colocarei algumas coisas que eu descobrir enquando fazia o curso

### @Table
A anotação @Table é usada para especificar o nome da tabela a ser criada no banco de dados para persistir a entidade anotada. Se você não especificar o nome da tabela, o nome da tabela será o nome da classe anotada com @Entity.

### @GeneratedValue
A anotação @GeneratedValue é usada para especificar a estratégia de geração de valor da chave primária. A estratégia de geração de valor da chave primária pode ser especificada usando a enumeração GenerationType. A enumeração GenerationType fornece as seguintes estratégias de geração de valor da chave primária:

- AUTO: A estratégia de geração de valor da chave primária será escolhida com base no provedor de persistência padrão.
- IDENTITY: A estratégia de geração de valor da chave primária será delegada para o banco de dados.
- SEQUENCE: A estratégia de geração de valor da chave primária será delegada para o banco de dados e usará a sequência especificada no @SequenceGenerator para gerar o valor da chave primária.
- TABLE: A estratégia de geração de valor da chave primária será delegada para o banco de dados e usará a tabela especificada no @TableGenerator para gerar o valor da chave primária.
- NONE: A estratégia de geração de valor da chave primária será definida para nenhuma.
- UUID: A estratégia de geração de valor da chave primária será definida para UUID.

Se você não especificar a estratégia de geração de valor da chave primária, o Hibernate usará a estratégia de geração de valor da chave primária AUTO.