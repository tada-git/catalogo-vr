# Template "Cadastrar Componente" — Artefatos para publicação

Este pacote contém **todos os artefatos mínimos** para publicar um novo *Software Template* no Backstage, partindo do arquivo fornecido. Você encontrará:

```
./novo-template-backstage
├── Template-MS-TMP.original.yaml                 # YAML original (somente referência)
├── template.alternativa-fetch-template.yaml      # Template pronto p/ uso com fetch:template
├── catalog-info.yaml                             # Location para registrar o template
├── mkdocs.yml                                    # TechDocs do template
├── docs/
│   └── index.md
└── skeleton/                                     # Esqueleto do componente gerado
    ├── README.md
    └── catalog-info.yaml
```

## Como publicar no Backstage

### Opção A — Registrar via UI
1. Suba este conteúdo para um repositório Git (ex.: `backstage-templates/novo-componente`).
2. No Backstage, acesse **Catalog → Register an existing component** e informe a URL do arquivo `catalog-info.yaml` deste repositório (não o do componente gerado).  
   Este `catalog-info.yaml` é do tipo **Location** e aponta para `template.alternativa-fetch-template.yaml`.

### Opção B — Registrar via configuração estática
Inclua uma *location* no `app-config.yaml` do Backstage:

```yaml
catalog:
  locations:
    - type: url
      target: https://SEU_GIT/SEU_REPO/path/para/catalog-info.yaml
      rules:
        - allow: [Template]
```
> Após adicionar ou alterar um template, **atualize/force o refresh** da *Location* no Backstage para ver as mudanças.  

## Pré‑requisitos
- Integração com o GitHub configurada no Backstage (para `publish:github`) e permissões adequadas para criar repositórios.  
- (Opcional) Se optar por usar a ação `roadiehq:utils:fs:write` em vez de `fetch:template`, é necessário instalar e registrar o módulo `@roadiehq/scaffolder-backend-module-utils` no backend do Backstage.

## Observações
- Este pacote inclui uma **versão alternativa** do template (`template.alternativa-fetch-template.yaml`) que usa somente ações *built-in* do Backstage, evitando depender de módulos adicionais.
- O arquivo `Template-MS-TMP.original.yaml` foi normalizado apenas para referência e preserva a estrutura original.

## Teste local
- Acesse **/create** para visualizar e executar o template.
- Em **/create/actions** você confere as ações disponíveis no seu ambiente.
