# GPG
## Verificar chaves no sistema operacional
gpg --list-secret-key --keyid-form LONG

## Criar nova chave
gpg --full-generate-key

## Exportar chave
gpg --armor --export [id da chave obtida através da listagem]

## Configurar Repositório
Adicionar ao GitHub a chave exportada

## Exportar variável de ambiente (adicionar no bash.profile)
export GPG_TTY=$(tty)

## Configurar Git
git config --global user.signingkey [id da chave obtida através da listagem]

git config --global commit.gpgsign true

git config --global tag.gpgsign true

## Criando Agent
* vim ~/.gnupg/gpg.conf
* use-agent
* ESC
* :wq
* gpgconf --launch gpg-agent

## Adicionando novo email na mesma chave
* gpg --edit-key [id da chave]
* adduid
* uid [número do id criado]
* trust
* save
