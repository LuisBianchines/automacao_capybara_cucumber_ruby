# automacao_capybara_cucumber_ruby

# INSTALAR RBENV NO LINUX

Passo 1 — Instalar o rbenv e dependências
O Ruby conta com vários pacotes que você pode instalar através do seu gerenciador de pacotes. Assim que eles estiverem instalados, instale o rbenv e use-o para instalar o Ruby:

Primeiramente, atualize sua lista de pacotes:

sudo apt update
 
Em seguida, instale as dependências necessárias para instalar o Ruby:

sudo apt install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm5 libgdbm-dev
 
Assim que baixar as dependências, instale o rbenv, propriamente dito. Clone o repositório rbenv do GitHub para o diretório ~/.rbenv:

git clone https://github.com/rbenv/rbenv.git ~/.rbenv
 
Em seguida, adicione ~/.rbenv/bin ao seu $PATH para que você possa usar o utilitário de linha de comando rbenv. Faça isso alterando seu arquivo ~/.bashrc para que ele afete as futuras sessões de login:

echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
 
Então, adicione o comando eval "$(rbenv init -)" ao seu arquivo ~/.bashrc para que o rbenv carregue automaticamente:

echo 'eval "$(rbenv init -)"' >> ~/.bashrc
 
Em seguida, aplique as alterações que você fez ao arquivo ~/.bashrc na sua sessão de shell atual:

source ~/.bashrc
 
Verifique se o rbenv está configurado corretamente usando o comando type, o qual irá mostrar mais informações sobre o comando rbenv:

type rbenv
 
Sua janela do terminal mostrará o seguinte:

Output
rbenv is a function
rbenv ()
{
    local command;
    command="${1:-}";
    if [ "$#" -gt 0 ]; then
        shift;
    fi;
    case "$command" in
        rehash | shell)
            eval "$(rbenv "sh-$command" "$@")"
        ;;
        *)
            command rbenv "$command" "$@"
        ;;
    esac
}
Em seguida, instale o plug-in ruby-build. Este plug-in adiciona o comando rbenv install que simplifica o processo de instalação para novas versões do Ruby:

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

# INSTALAR RUBY COM RUBY-BUILD

om o plug-in do ruby-build instalado, você pode instalar as versões do Ruby que precisar através de um simples comando. Primeiramente, vamos listar todas as versões disponíveis do Ruby:

rbenv install -l
 
O resultado desse comando deve ser uma longa lista de versões que você pode escolher para instalar.

Vamos instalar o Ruby 2.5.1:

rbenv install 2.5.1
 
A instalação do Ruby pode ser um processo longo, então esteja preparado.

Assim que terminar de instalar, ajuste-o como a nova versão padrão do Ruby com o sub-comando global:

rbenv global 2.5.1
 
Verifique se o Ruby foi devidamente instalado verificando seu número de versão:

ruby -v
 
Se a versão instalada do Ruby for a 2.5.1, seu resultado para o comando acima deve ficar com uma aparência como esta:

Output
ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-linux]
Para instalar e usar uma versão diferente do Ruby, execute os comandos rbenv com um número diferente de versão, como em rbenv install 2.3.0 e rbenv global 2.3.0.

Agora, você tem pelo menos uma versão do Ruby instalada e definiu sua versão padrão do Ruby. Em seguida, vamos configurar gems e Rails.

# INSTALANDO O BUNDLER

gem install bundler 