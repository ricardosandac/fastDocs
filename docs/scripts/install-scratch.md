---
title: install-scratch.bat
summary: Script para configurar um scratch org do Salesforce para o projeto E-Bikes.
---

# install-scratch.bat

## Descrição
O script `install-scratch.bat` automatiza a configuração de um scratch org do Salesforce para o projeto E-Bikes. Ele realiza etapas como criação do scratch org, implantação do código-fonte, atribuição de permissões e importação de dados de exemplo.

## Etapas do Script

1. **Limpeza de scratch orgs anteriores**:
   - Comando: `sf org delete scratch -p -o %ORG_ALIAS%`
   - Remove qualquer scratch org existente com o alias especificado.

2. **Criação de um novo scratch org**:
   - Comando: `sf org create scratch -f config/project-scratch-def.json -a %ORG_ALIAS% -d -y 30`
   - Cria um novo scratch org com base no arquivo de definição `project-scratch-def.json`.

3. **Implantação do código-fonte**:
   - Comando: `sf project deploy start`
   - Faz o deploy do código-fonte do projeto para o scratch org.

4. **Atribuição de conjuntos de permissões**:
   - Comando: `sf org assign permset -n ebikes`
   - Atribui o conjunto de permissões `ebikes` ao scratch org.

5. **Importação de dados de exemplo**:
   - Comando: `sf data tree import -p data/sample-data-plan.json`
   - Importa dados de exemplo usando o plano de dados `sample-data-plan.json`.

6. **Publicação do site XP Cloud**:
   - Comando: `sf community publish -n E-Bikes`
   - Publica a comunidade `E-Bikes` no XP Cloud.

7. **Implantação do perfil de convidado**:
   - Comando: `sf project deploy start --metadata-dir=guest-profile-metadata -w 10`
   - Faz o deploy do perfil de convidado para o site XP Cloud.

## Exemplo de Uso
Este script pode ser executado diretamente no terminal:
```bash
bin\install-scratch.bat
```

## Relacionamentos

- Utiliza: [Salesforce CLI](https://developer.salesforce.com/tools/sfdxcli).