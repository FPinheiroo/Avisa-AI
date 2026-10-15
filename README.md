# Vigilanse - Especificação e Integração de Componentes (Lab 4)

## 1. Tecnologias Utilizadas
- **Linguagem:** TypeScript
- **Plataforma:** React Native / Node.js
- **Framework de Testes:** Jest

## 2. Estrutura dos Componentes
- `src/services/DriverAuthService.ts`: Implementação do Componente 1 (Autenticação e Gestão de Motoristas).
- `src/services/IncidentService.ts`: Implementação do Componente 2 (Gestão e Registro de Ocorrências).
- `src/types/index.ts`: Interfaces de Contratos e DTOs.
- `src/__tests__/integration.test.ts`: Testes unitários e de integração entre componentes.

## 3. Interfaces e Operações Implementadas
- **IDriverAuthService**: `registerDriver`, `authenticateDriver`, `validateToken`.
- **IIncidentService**: `registerIncident` (depende de `IDriverAuthService`).

## 4. Comunicação entre Componentes
O componente `IncidentService` recebe por injeção de dependência o `DriverAuthService`. Ao receber uma solicitação de registro de ocorrência, `IncidentService` valida a sessão do token chamando a operação `validateToken` do `DriverAuthService`.

## 5. Instruções para Execução e Testes
1. Instalar dependências:
   ```bash
   npm install
2. Executar os testes:
    npm test