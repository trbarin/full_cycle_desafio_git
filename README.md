# GPG
## Verificar chaves no sistema operacional
gpg --list-secret-key --keyid-form LONG

## Criar nova chave
gpg --full-generate-key

## Exportar chave
gpg --armor --export [id da chave obtida através da listagem]

##
Adicionar ao GitHub a chave exportada

## Exportar variável de ambiente (adicionar no bash.profile)
export GPG_TTY=$(tty)

## Configurar Git
git config --global user.signingkey [id da chave obtida através da listagem]

git config --global commit.gpgsign true

git config --global tag.gpgsign true

## Criando Agent
* vim ~/.gnupg/gpg.conf
* user-agent
* ESC
* :wq
* gpgconf --launch gpg-agent

