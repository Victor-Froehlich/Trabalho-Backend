# \# 🥟 Baozi Store — API REST

# 

# > Sistema de gerenciamento de clientes, produtos e pedidos para uma pequena loja de pão chinês.  

# > Desenvolvido com \*\*Java + Spring Boot\*\* como atividade prática da disciplina de Desenvolvimento Web Back-End.

# 

# ---

# 

# \## 📋 Índice

# 

# \- \[Sobre o Projeto](#-sobre-o-projeto)

# \- \[Tecnologias](#-tecnologias)

# \- \[Estrutura do Projeto](#-estrutura-do-projeto)

# \- \[Como Rodar](#-como-rodar)

# \- \[Endpoints da API](#-endpoints-da-api)

# \- \[Exemplos de Requisição](#-exemplos-de-requisição)

# \- \[Banco de Dados](#-banco-de-dados)

# \- \[Autor](#-autor)

# 

# ---

# 

# \## 📖 Sobre o Projeto

# 

# A \*\*Baozi Store\*\* é uma loja que vende pão chinês e precisava informatizar seu controle básico de operações. Esta API REST permite:

# 

# \- Cadastrar e gerenciar \*\*clientes\*\*

# \- Cadastrar e gerenciar \*\*produtos\*\*

# \- Registrar \*\*pedidos\*\* vinculando cliente, produto e quantidade

# 

# ---

# 

# \## 🛠 Tecnologias

# 

# | Tecnologia | Versão |

# |---|---|

# | Java | 17+ |

# | Spring Boot | 3.2.5 |

# | Spring Data JPA | 3.2.5 |

# | H2 Database | (em memória) |

# | Maven | 3.x |

# 

# ---

# 

# \## 📁 Estrutura do Projeto

# 

# ```

# baozi-store/

# ├── src/

# │   └── main/

# │       ├── java/com/baozistore/

# │       │   ├── BaoziStoreApplication.java

# │       │   ├── controller/

# │       │   │   ├── ClienteController.java

# │       │   │   ├── ProdutoController.java

# │       │   │   └── PedidoController.java

# │       │   ├── model/

# │       │   │   ├── Cliente.java

# │       │   │   ├── Produto.java

# │       │   │   └── Pedido.java

# │       │   └── repository/

# │       │       ├── ClienteRepository.java

# │       │       ├── ProdutoRepository.java

# │       │       └── PedidoRepository.java

# │       └── resources/

# │           └── application.properties

# └── pom.xml

# ```

# 

# ---

# 

# \## 🚀 Como Rodar

# 

# \### Pré-requisitos

# 

# \- Java 17 ou superior instalado

# \- IntelliJ IDEA (recomendado) ou qualquer IDE com suporte a Maven

# 

# \### Passo a passo

# 

# \*\*1. Clone o repositório\*\*

# ```bash

# git clone https://github.com/SEU\_USUARIO/baozi-store.git

# cd baozi-store

# ```

# 

# \*\*2. Abra no IntelliJ IDEA\*\*

# ```

# File → Open → selecione a pasta baozi-store

# ```

# Aguarde o Maven baixar as dependências automaticamente.

# 

# \*\*3. Execute a aplicação\*\*

# 

# Clique no botão ▶ na classe `BaoziStoreApplication.java` ou rode via terminal:

# ```bash

# mvn spring-boot:run

# ```

# 

# \*\*4. Acesse a API\*\*

# ```

# http://localhost:8080

# ```

# 

# \*\*5. Console do banco H2 (opcional)\*\*

# ```

# http://localhost:8080/h2-console

# JDBC URL: jdbc:h2:mem:baozidb

# User: sa

# Password: (vazio)

# ```

# 

# ---

# 

# \## 📡 Endpoints da API

# 

# \### Cliente

# 

# | Método | Endpoint | Descrição | Status |

# |---|---|---|---|

# | `POST` | `/clientes` | Criar cliente | 201 Created |

# | `GET` | `/clientes` | Listar todos | 200 OK |

# | `GET` | `/clientes/{id}` | Buscar por ID | 200 OK |

# | `PUT` | `/clientes/{id}` | Atualizar | 200 OK |

# | `DELETE` | `/clientes/{id}` | Apagar | 204 No Content |

# 

# \### Produto

# 

# | Método | Endpoint | Descrição | Status |

# |---|---|---|---|

# | `POST` | `/produtos` | Criar produto | 201 Created |

# | `GET` | `/produtos` | Listar todos | 200 OK |

# | `GET` | `/produtos/{id}` | Buscar por ID | 200 OK |

# | `PUT` | `/produtos/{id}` | Atualizar | 200 OK |

# | `DELETE` | `/produtos/{id}` | Apagar | 204 No Content |

# 

# \### Pedido

# 

# | Método | Endpoint | Descrição | Status |

# |---|---|---|---|

# | `POST` | `/pedidos` | Criar pedido | 201 Created |

# | `GET` | `/pedidos` | Listar todos | 200 OK |

# | `GET` | `/pedidos/{id}` | Buscar por ID | 200 OK |

# | `PUT` | `/pedidos/{id}` | Atualizar | 200 OK |

# | `DELETE` | `/pedidos/{id}` | Apagar | 204 No Content |

# 

# ---

# 

# \## 💡 Exemplos de Requisição

# 

# \### Criar Cliente

# ```http

# POST /clientes

# Content-Type: application/json

# 

# {

# &nbsp; "nome": "Victor4280972",

# &nbsp; "clienteDesde": "2024-01-15"

# }

# ```

# 

# \*\*Resposta:\*\*

# ```json

# {

# &nbsp; "id": 1,

# &nbsp; "nome": "Victor4280972",

# &nbsp; "clienteDesde": "2024-01-15"

# }

# ```

# 

# ---

# 

# \### Criar Produto

# ```http

# POST /produtos

# Content-Type: application/json

# 

# {

# &nbsp; "nome": "Baozi Tradicional",

# &nbsp; "preco": 5.90,

# &nbsp; "estoque": true

# }

# ```

# 

# \*\*Resposta:\*\*

# ```json

# {

# &nbsp; "id": 1,

# &nbsp; "nome": "Baozi Tradicional",

# &nbsp; "preco": 5.90,

# &nbsp; "estoque": true

# }

# ```

# 

# ---

# 

# \### Criar Pedido

# ```http

# POST /pedidos

# Content-Type: application/json

# 

# {

# &nbsp; "clienteId": 1,

# &nbsp; "produtoId": 1,

# &nbsp; "quantidade": 3

# }

# ```

# 

# \*\*Resposta:\*\*

# ```json

# {

# &nbsp; "id": 1,

# &nbsp; "clienteId": 1,

# &nbsp; "produtoId": 1,

# &nbsp; "quantidade": 3

# }

# ```

# 

# ---

# 

# \## 🗄 Banco de Dados

# 

# O projeto usa \*\*H2\*\* — banco relacional em memória que não requer instalação. Os dados são resetados a cada reinício da aplicação.

# 

# Para usar \*\*MySQL\*\*, descomente as linhas no `application.properties`:

# 

# ```properties

# \# spring.datasource.url=jdbc:mysql://localhost:3306/baozidb?createDatabaseIfNotExist=true

# \# spring.datasource.username=root

# \# spring.datasource.password=sua\_senha

# \# spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# \# spring.jpa.database-platform=org.hibernate.dialect.MySQLDialect

# ```

# 

# E adicione a dependência no `pom.xml`:

# ```xml

# <dependency>

# &nbsp;   <groupId>com.mysql</groupId>

# &nbsp;   <artifactId>mysql-connector-j</artifactId>

# &nbsp;   <scope>runtime</scope>

# </dependency>

# ```

# 

# \### Diagrama de Entidades

# 

# ```

# CLIENTE                 PRODUTO

# ───────                 ───────

# id        Long          id        Long

# nome      String        nome      String

# clienteDesde LocalDate  preco     BigDecimal

# &nbsp;                       estoque   Boolean

# &nbsp;   │                       │

# &nbsp;   └──────── PEDIDO ────────┘

# &nbsp;             ──────

# &nbsp;             id         Long

# &nbsp;             clienteId  Long

# &nbsp;             produtoId  Long

# &nbsp;             quantidade Integer

# ```

# 

# ---

# 

# \## 👤 Autor

# 

# \*\*Victor4280972\*\*  

# Disciplina: Desenvolvimento Web Back-End  

# Professora: Luciane Kanashiro, Me  

# Instituição: UNINTER

# 

# ---

# 

# <p align="center">

# &nbsp; Feito com ☕ e muito pão chinês 🥟

# </p>

