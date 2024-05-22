#### Ansible

Projetos e estudos sobre Ansible.

![Ansible](https://miro.medium.com/v2/resize:fit:1400/1*ZAJs0AuKVdnRSqOS8Mw3Kg.png)

#### Anotações

Ansible, ferramenta para gerenciar, automatizar, configurar servidores e implantar aplicativos a partir de uma localização central.

#### Arquitetura

- **Control Node e Managed Hosts**
- **Control Machine: Instalacão do Ansible**
- **Managed Host: Host Inventory**
- **Host Inventory: Arquivo de texto (control node), com a lista de hosts / Ip`s que serão gerenciados pelo Ansible**
- **Comunicação via SSH**
- **Não há necessidade da instalação local de softwares para a distribuição no Managed Hot** 

--------

- **Code Modules**
São scripts reutilizáveis que realizam tarefas específicas, como instalar pacotes, copiar arquivos ou gerenciar serviços. O Ansible vem com centenas de módulos predefinidos que facilitam a automação de diversas tarefas em diferentes sistemas e aplicações.

- **Custom Modules**
Quando os módulos predefinidos não atendem às necessidades específicas, os usuários podem criar seus próprios módulos personalizados. Esses módulos podem ser escritos em qualquer linguagem de programação que possa retornar JSON, como Python, Perl ou Ruby.

- **Playbooks**
São arquivos YAML que definem um conjunto de instruções a serem executadas em hosts gerenciados. Os playbooks organizam tarefas em uma sequência lógica e podem incluir variáveis, loops e condicionais para flexibilidade e controle detalhado.

- **Plugins**
São componentes que ampliam as funcionalidades do Ansible. Existem vários tipos de plugins, como plugins de conexão, plugins de autenticação, plugins de cache, entre outros. Eles permitem personalizar o comportamento de diferentes aspectos do Ansible sem modificar o código-fonte principal.

- **Host Inventory**
É uma lista de máquinas gerenciadas pelo Ansible. Pode ser um arquivo estático (geralmente em formato INI ou YAML) ou dinâmico, gerado a partir de fontes externas (como CMDBs, cloud providers, etc.). O inventário define quais hosts são alvos das operações de automação.

- **Ansible [Galaxy](https://galaxy.ansible.com/ui/)** 
É uma plataforma comunitária onde os usuários podem encontrar, compartilhar e colaborar em papéis (roles) do Ansible. Um role é um conjunto reutilizável de tarefas, variáveis, templates e arquivos que podem ser usados para configurar partes de um sistema ou aplicação. O Ansible Galaxy facilita a reutilização de configurações complexas e promove a colaboração entre desenvolvedores e administradores.

--------

#### Comandos 

- ansible --version

**Listas todos os Hosts**

- ansible all -i hosts --list-hosts

- ansible all -i hosts -m ping

- ansible-playbook -i hosts playbook.yml -b 

**Become**

O parâmetro -b ou --become permite executar o comando com privilégios elevados.

**Copiar arquivos**

- ansible all -i hosts -m copy -a "src=./copy.txt dest=/copy.txt" -b

**Reiniciar**

- ansible all -i hosts -m reboot -b 

- ansible all -i hosts -m apt -a "name=nginx update_cache=yes" -b

**Remove pacote**

- ansible all -i hosts -m apt -a "name=curl state=absent"

**Instala pacotes**

- ansible all -i hosts -m apt -a "name=curl state=present"

**Parar Services**

- ansible all -i hosts -m service -a "name=nginx state=stopped"

**chave_ssh**

- ssh-keygen -t rsa -b 2048

**Configurar chave ssh com senha**

- ssh-agent bash
- ssh-add "caminho da chave"

**Verbose**

Para ver quais tarefas estão sendo executadas durante a execução de um playbook ou comando Ansible, você pode usar a opção -v ou --verbose. 

Isso fornecerá informações mais detalhadas durante a execução.

Aqui estão algumas opções que você pode usar:

- -v ou --verbose: 

Exibe informações verbosas durante a execução.

- -vvv: 

Exibe informações de depuração. Essa opção é útil para depurar problemas ou verificar detalhes específicos durante a execução.

- -vvvv: 

Exibe informações de depuração mais detalhadas. Isso pode ser útil para depurar problemas complexos ou obter um registro detalhado das operações executadas.


