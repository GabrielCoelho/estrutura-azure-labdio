# Arquitetura do Microsoft Azure: Componentes e Estrutura

![Azure Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Microsoft_Azure.svg/800px-Microsoft_Azure.svg.png)

## 📋 Sobre o Projeto

Este repositório foi criado como parte do desafio de projeto da DIO, focado no estudo dos componentes arquitetônicos fundamentais do Microsoft Azure. Nele, documentei os principais conceitos da infraestrutura física e de gerenciamento do Azure, explorando desde regiões e zonas de disponibilidade até recursos, assinaturas e grupos de gerenciamento.

## 🏗️ Componentes Arquitetônicos do Azure

A arquitetura do Azure pode ser dividida em dois agrupamentos principais:
- **Infraestrutura Física**: Os componentes físicos e geográficos que sustentam os serviços
- **Infraestrutura de Gerenciamento**: Os componentes de organização e administração dos recursos

### 1. Infraestrutura Física

#### 1.1 Datacenters

- Instalações físicas com recursos organizados em racks
- Equipados com energia, refrigeração e infraestrutura de rede dedicadas
- Não são diretamente acessíveis aos usuários
- Agrupados em regiões e zonas de disponibilidade

#### 1.2 Regiões

- Áreas geográficas que contêm pelo menos um datacenter (geralmente vários)
- Conectados por redes de baixa latência
- O Azure oferece mais de 60 regiões em mais de 140 países
- Permitem que você escolha a localização mais próxima dos usuários
- Preservam a residência de dados para conformidade regulatória

#### 1.3 Zonas de Disponibilidade

- Datacenters fisicamente separados dentro de uma região
- Cada zona possui:
  - Energia independente
  - Refrigeração independente
  - Rede independente
- Conectadas por redes privadas de fibra óptica de alta velocidade
- Projetadas como limite de isolamento (se uma falhar, as outras continuam operando)
- Ideal para aplicações críticas que necessitam de alta disponibilidade

#### 1.4 Pares de Regiões

- A maioria das regiões é emparelhada com outra região na mesma geografia
- Separadas por pelo menos 300 milhas (480 km)
- Vantagens:
  - Replicação de recursos para reduzir impacto de desastres naturais
  - Priorização de restauração em caso de interrupção ampla
  - Atualizações distribuídas sequencialmente para minimizar tempo de inatividade
  - Dados residindo na mesma geografia para fins de jurisdição

#### 1.5 Regiões Soberanas

- Instâncias isoladas do Azure para fins de conformidade ou requisitos legais
- Exemplos:
  - US DoD Central, US Gov Virginia, US Gov Iowa: para órgãos do governo dos EUA
  - Leste da China, Norte da China: operadas pela 21Vianet em parceria com a Microsoft

### 2. Infraestrutura de Gerenciamento

#### 2.1 Recursos e Grupos de Recursos

- **Recursos**: Componentes disponíveis para criar soluções (VMs, armazenamento, redes, bancos de dados, etc.)
- **Grupos de Recursos**: Contêineres para gerenciar e agregar recursos em uma única unidade
- Características dos Grupos de Recursos:
  - Um recurso só pode existir em um grupo de recursos
  - Os recursos podem existir em diferentes regiões dentro do mesmo grupo
  - Os recursos podem ser movidos entre grupos
  - Os aplicativos podem utilizar vários grupos

#### 2.2 Assinaturas

- Fornecem acesso autenticado e autorizado às contas do Azure
- Funcionam como limites para:
  - Cobrança: relatórios e faturas separados por assinatura
  - Controle de acesso: gerenciamento de permissões por assinatura
- Uma empresa pode usar uma única conta com múltiplas assinaturas para diferentes departamentos

#### 2.3 Grupos de Gerenciamento

- Permitem organizar assinaturas em hierarquias para gerenciamento eficiente
- As assinaturas herdam condições aplicadas ao grupo de gerenciamento
- Facilitam a governança em grande escala

## 🔐 Contas do Azure

### Tipos de Contas

1. **Conta Gratuita do Azure**
   - Acesso gratuito a produtos populares por 12 meses
   - Crédito inicial para uso nos primeiros 30 dias
   - Acesso a mais de 25 produtos sempre gratuitos

2. **Conta de Estudante Gratuita**
   - Acesso gratuito a determinados produtos por 12 meses
   - Crédito de US$ 100 para uso nos primeiros 12 meses
   - Ferramentas gratuitas para desenvolvedores
   - Não requer cartão de crédito

3. **Área Restrita do Microsoft Learn**
   - Assinatura temporária para treinamento
   - Permite criar recursos durante os módulos de aprendizado
   - Recursos são limpos automaticamente ao concluir os módulos

## 🔄 Hierarquia de Organização

A estrutura organizacional do Azure segue esta hierarquia:

```
Grupos de Gerenciamento
    └── Assinaturas
         └── Grupos de Recursos
              └── Recursos
```

## 🎓 Considerações Finais

Durante o desenvolvimento deste projeto, pude aprofundar meu entendimento sobre a arquitetura fundamental do Azure. Compreender como a Microsoft estruturou sua nuvem desde os datacenters físicos até a organização lógica dos recursos me proporcionou uma visão mais clara de como implementar soluções eficientes e resilientes na plataforma.

A robustez da infraestrutura física com suas regiões distribuídas globalmente e zonas de disponibilidade demonstra o compromisso com alta disponibilidade e recuperação de desastres. Já a estrutura de gerenciamento oferece a flexibilidade necessária para organizar recursos conforme as necessidades específicas de cada negócio.

Este conhecimento é essencial para qualquer profissional que deseja trabalhar com o Azure, pois forma a base para decisões de arquitetura e implementação de soluções em nuvem.

## 📚 Referências

- Material didático do curso AZ-900: Introdução aos Conceitos Básicos do Microsoft Azure
- Documentação oficial do Microsoft Azure: [Azure Documentation](https://docs.microsoft.com/pt-br/azure/)
- Portal de infraestrutura global do Azure: [Azure Global Infrastructure](https://azure.microsoft.com/global-infrastructure/)

---

*Projeto desenvolvido por Gabriel Coelho Soares para o Bootcamp da DIO - 2025*
