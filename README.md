# ServerlessMinds
Plataforma de Cursos sobre Arquitetura, Serverless e AWS

### Objetivo

Desenvolver uma plataforma de cursos que forneça treinamento especializado em arquitetura de software, tecnologias serverless e AWS. A plataforma deve oferecer funcionalidades de cadastro de usuários, criação de cursos, gerenciamento de conteúdos e acompanhamento de progresso dos alunos.

### Requisitos

#### Requisitos Funcionais:

- **Cadastro de Usuários:**
  - O sistema deve permitir o cadastro de novos usuários via POST, através do schema: { "nome": "John Doe", "email": "johndoe@example.com", "senha": "password123" }
  - Validação de e-mail único e senha segura.
  - Resposta em caso de sucesso:
    - Código HTTP: 201
    - Mensagem: user created successfully
  - Resposta em caso de falha (e-mail já cadastrado):
    - Código HTTP: 409
    - Mensagem: email already in use

- **Criação de Cursos:**
  - O sistema deve permitir que administradores criem novos cursos via POST, através do schema: { "titulo": "Curso de AWS", "descricao": "Aprenda AWS do zero ao avançado", "conteudo": ["Módulo 1", "Módulo 2"] }
  - Validação de campos obrigatórios e formato correto.
  - Resposta em caso de sucesso:
    - Código HTTP: 201
    - Mensagem: course created successfully
  - Resposta em caso de falha (dados inválidos):
    - Código HTTP: 422
    - Mensagem: invalid course data

- **Gerenciamento de Conteúdos:**
  - O sistema deve permitir que administradores adicionem, editem e removam conteúdos dos cursos.
  - Validação de permissões de administrador.

- **Acompanhamento de Progresso:**
  - O sistema deve permitir que os alunos acompanhem seu progresso nos cursos.
  - Exibição de módulos concluídos e próximos passos recomendados.

### Dicas:

- Utilize tecnologias serverless, como AWS Lambda, para a implementação dos serviços.
- Utilize Amazon S3 para o armazenamento de conteúdos estáticos (vídeos, documentos).
- Utilize Amazon DynamoDB para o armazenamento de dados dos usuários, cursos e progresso.
- Utilize Amazon Cognito para a gestão de autenticação e autorização dos usuários.
- Para dúvidas sobre a implementação de serviços serverless, consulte a documentação oficial da AWS [aqui](https://docs.aws.amazon.com/).
- Para mais informações sobre arquitetura serverless, você pode clicar [aqui](https://aws.amazon.com/serverless/).

### Entrega:

- O código-fonte completo da implementação.
- Documentação explicando como rodar o projeto em ambiente de desenvolvimento.
- Utilize docker/docker-compose para que possamos realizar os testes de sua aplicação.

### Como rodar a aplicação?

1. **Requisitos:** 
   - Certifique-se de ter o Node.js instalado em sua máquina.
   - Certifique-se de ter o Docker instalado em sua máquina.

```bash
git clone https://github.com/seuprojeto/serverlessminds.git
```

2. Acesse a pasta do app:

```bash
cd serverlessminds
```

3. Rode o docker para subir os serviços necessários:

```bash
docker-compose up -d
```

4. Execute as migrações e seeders para popular o banco de dados com dados iniciais.

```bash
npm run migrate
npm run seed
```

5. Inicie a aplicação:

```bash
npm start
```