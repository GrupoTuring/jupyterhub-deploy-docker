# Cuidando do Alan

## Introdução

O Alan é um computador do Grupo Turing, financiado pelo Amigos da Póli e que podemos usar para executar nossos códigos, treinar modelos e o que mais quisermos.
Atualmente ele está na casa do [Noel](https://github.com/anor4k), ligado 24/7 e com um nobreak para evitar que desligue durante pequenas quedas de energia.
Também possui uma conexão de 1Gbps, e IP fixo associado à url [alan.grupoturing.com.br](https://alan.grupoturing.com.br).
As urls [pc.grupoturing.com.br](https://pc.grupoturing.com.br) e [turingpc.anorak.dev](https://turingpc.anorak.dev) também funcionam, mas não são devidamente configuradas.

## Avisos Importantes

- **Tenha backup de todos seus arquivos**, projetos, datasets e configurações importantes no Jupyter. O ambiente possui persistência, mas não somos especialistas e durante alguma manutenção, pode haver o reset dos ambientes. Tentaremos evitar ao máximo, mas use o Google Drive, GitHub, e seu computador pessoal para armazenar todo seu trabalho.
- **Você não é a única pessoa usando o computador!** Lembre-se de desligar seu notebook quando parar de usar, e tente usar seus recursos de forma eficiente.
- **A disponibilidade não é garantida.** O computador fica ligado em uma residência, e não há garantia de uptime, redundância ou mesmo disponibilidade de manutenção. Se você precisa executar tarefas realmente críticas, é melhor ir atrás de um ambiente em nuvem ou outra hospedagem profissional.

## Especificações

|  | |
|---|---|
| CPU | Intel i7-8700 @ 3.20GHz |
| RAM | 32GiB (4x8GiB) @ 2400MHz |
| GPU | NVIDIA GeForce 1060 6GB |
| SSD | Kingston 240GB |
| HDD | Seagate 1TB |
| OS | Ubuntu 18.04 LTS |

## JupyterHub

No dia a dia, o Jupyter é uma das ferramentas mais úteis pra um cientista de dados.
Para suprir essa necessidade, instalamos o JupyterHub como solução para usar notebooks remotamente e executar códigos de experimentação e exploração.

Para acessar o JupyterHub, você deve [acessar o Alan por um navegador](https://alan.grupoturing.com.br) e fazer login com sua conta do GitHub.
Se você fizer parte da organização [GrupoTuring no GitHub](https://github.com/GrupoTuring), conseguirá entrar com sucesso.

Quando entrar, é só clicar em "Start My Server" e você será redirecionado para uma página do JupyterLab, onde você pode rodar notebooks usando o kernel de sua preferência, além de poder acessar um terminal e usar a linha de comando normalmente.
Cada um dos usuários do JupyterHub possui um ambiente completamente isolado dos demais. Lembre-se de desligar o seu servidor quando não estiver usando (File > Hub Control Panel > Stop My Server), para não correr o risco de usar recursos à toa. No futuro vamos implementar gerenciamento automático desses recursos.

## SSH e VNC

Caso a interface do Jupyter não seja suficiente para o que você precisa fazer, você pode acessar diretamente o computador através de uma conexão SSH. O comando `ssh turing@alan.grupoturing.com.br -p 2222` vai permitir que você se conecte com o usuário do Turing diretamente ao servidor pela linha de comando.
Se quiser utilizar a interface gráfica através de VNC, o comando `ssh -L 5901:0.0.0.0:5901 -X turing@alan.grupoturing.com.br -p 2222` permite que você use um cliente VNC (como o [TightVNC](https://www.tightvnc.com/download.php)) com o endereço `localhost:5901` para acessar de forma segura usando um túnel SSH. A porta 5901 *não* ficará exposta para a internet.
As senhas de acesso não ficarão registradas nesse documento por motivos de segurança, mas estarão disponíveis para todos.

## Solução de Problemas

- ### Sou parte da organização no GitHub mas recebo um erro ao logar no JupyterHub!

  - Na [página de membros da organização](https://github.com/orgs/GrupoTuring/people), confira se sua visibilidade está como "pública". Estamos tentando remover essa necessidade, mas por enquanto essa ação é necessária.
  - Se você não for parte da organização no GitHub, mas for parte do Grupo Turing, entre em contato com algum dos diretores ou líderes de área do grupo para ser incluído!

- ### Estou com problema X no JupyterHub // Preciso de função X disponível para utilizar
  
  - Todos os ambientes possuem o Anaconda disponível, o que deve fornecer as ferramentas necessárias para a grande maioria dos casos. Estamos analisando como configurar a imagem dos notebooks para permitir acesso root total aos usuários.
  - Além disso, a instalação usada para disponibilizar o JupyterHub e criar os notebooks possui uma gama muito extensa de configurações, o que nos dá muita flexibilidade e controle, mas também torna difícil algumas etapas da configuração. Você pode [abrir uma Issue no GitHub](https://github.com/GrupoTuring/jupyterhub-deploy-docker/issues) detalhando seu problema, ou [criar um Pull Request](https://github.com/GrupoTuring/jupyterhub-deploy-docker/pulls) com a solução, que tentaremos resolver e atualizar o sistema.

- ### Eu li todo esse manual mas ainda preciso de ajuda, socorro!
  
  - Tudo bem, fique tranquilo! Pode perguntar à vontade nos grupos do WhatsApp, no Discord, ou mandar uma mensagem diretamente para o [Noel](https://wa.me/5516981268981), que é o principal responsável pelo Alan atualmente.
