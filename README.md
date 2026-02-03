# 🚀 Workshop CI/CD - Java Academy Demo

Aplicação Spring Boot + Gradle para demonstração de CI/CD.

## 📋 Sobre

Este projeto foi criado especificamente para o Workshop CI/CD da **Rumos - Academia Java**.

**Objectivo:** Demonstração prática de pipelines de CI/CD com código Java real.

## 🏗️ Stack Tecnológica

| Componente | Tecnologia | Versão |
|-------------|-----------|--------|
| Linguagem | Java | 17 |
| Framework | Spring Boot | 3.2.0 |
| Build Tool | Gradle | 8.x |
| Testes | JUnit 5 | 5.10.1 |
| CI/CD | GitHub Actions | - |

## 🚀 Como Correr Localmente

### Pré-requisitos
- JDK 17+
- Gradle (ou usar wrapper)

### Passos

```bash
# Clone do repositório
git clone <repository-url>
cd java-demo-project

# Executar a aplicação
./gradlew bootRun

# Ou via gradle instalado
gradle bootRun
```

### Acesso

```
Homepage:     http://localhost:8080
Health Check: http://localhost:8080/actuator/health
API Docs:     (Swagger seria aqui em produção)
```

## 🧪 Testes

```bash
# Executar todos os testes
./gradlew test

# Executar testes com debug
./gradlew test --info

# Gerar relatório de cobertura
./gradlew jacocoTestReport

# Verificar cobertura
./gradlew jacocoTestCoverageVerification
```

### Relatórios

- **Testes:** `build/reports/tests/test/index.html`
- **Cobertura:** `build/reports/jacoco/test/html/index.html`

## 📦 Build

```bash
# Criar JAR executável
./gradlew clean build

# JAR fica em: build/libs/
```

## 🐳 Docker (Opcional)

```bash
# Build da imagem
docker build -t workshop-cicd:latest .

# Executar container
docker run -p 8080:8080 workshop-cicd:latest
```

## 🌐 Endpoints da API

| Método | Endpoint | Descrição |
|--------|-----------|-----------|
| GET | `/` | Homepage com informações |
| GET | `/actuator/health` | Health check (CI/CD) |
| GET | `/api/version` | Versão da aplicação |
| GET | `/api/users` | Lista todos os utilizadores |
| GET | `/api/users/{id}` | Detalhes do utilizador |
| GET | `/api/calculate/{a}/{b}` | Calculadora demo |
| GET | `/api/status/{code}` | Status response (demo) |

## 🔄 CI/CD

O projecto inclui 3 workflows no GitHub Actions:

### 1. CI/CD Pipeline (`ci.yml`)
Pipeline completa com:
- Lint e verificação de código
- Testes em múltiplas versões Java
- Build do JAR
- Security scan
- Deploy staging/production
- Rollback automático em caso de falha

### 2. Rollback Manual (`rollback.yml`)
Permite rollback manual para qualquer versão anterior.

### 3. Daily Security Check (`daily-scheduled.yml`)
Verificações automáticas de segurança e dependências.

## 📊 Qualidade

O projecto está configurado com gates de qualidade:

| Gate | Critério | Em que etapa? |
|------|-----------|--------------|
| Testes passam | 100% de testes | Job `test` |
| Cobertura | Mínimo 70% | Job `test` |
| Lint | Padrões de código | Job `lint` |
| Security | Sem CVE críticos | Job `security` |

## 🎯 Objetivos do Workshop

Após concluir o workshop, serás capaz de:

1. ✅ Compreender os conceitos de CI/CD
2. ✅ Configurar pipelines de CI/CD para projetos Java
3. ✅ Implementar testes como gates de qualidade
4. ✅ Automatizar builds e deploys
5. ✅ Executar rollbacks manuais
6. ✅ Monitorizar aplicações em produção

## 📚 Recursos

- [Spring Boot Docs](https://spring.io/projects/spring-boot)
- [Gradle User Guide](https://docs.gradle.org/current/userguide/userguide.html)
- [JUnit 5 Docs](https://junit.org/junit5/docs/current/user-guide/)
- [GitHub Actions Docs](https://docs.github.com/en/actions)

## 🤝 Rumos Formação

**Academia Programador Java** - Workshop CI/CD

---

*Created for CI/CD Workshop*
