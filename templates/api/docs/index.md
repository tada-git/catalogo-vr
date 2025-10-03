# Template: Cadastrar Componente

Este repositório contém um *Software Template* do Backstage para cadastrar novos componentes (serviço, web, mobile, biblioteca) com governança padronizada.

## Parâmetros
- **tipoComponente**: (servico, web, mobile, biblioteca)
- **nome**: identificador do componente (ex: `ms-pagamentos`, `svc-relatorios`)
- **descricao**: descrição funcional
- **versao**: versão inicial (ex: 1.0.0)
- **responsavel**: grupo dono do componente
- **tipoExposicaoEModeloAcesso**: tags de exposição e acesso

## Etapas do template
1. **Fetch Skeleton**: materializa os arquivos base do componente.
2. **Publish**: cria o repositório no GitHub e faz o primeiro commit.
3. **Register**: registra o `catalog-info.yaml` no catálogo do Backstage.

## Saídas
- Link do repositório criado.
- Link para abrir a entidade no catálogo.
