##Ansible
Projetos e estudos sobre Ansible.

Ferramenta para gerenciar, automatizar, configurar servidores e implantar aplicativos a partir de uma localização central.

![Ansible](https://sretips.com.br/images/iac/ansible.png)

#### Anotações

ansible --version

**chave_ssh**
ssh-keygen -t rsa -b 2048

**Listas todos os Hosts**
ansible all -i hosts --list-hosts

ansible all -i hosts -m ping

**O parâmetro -b ou --become permite executar o comando com privilégios elevados.**

**Copiar arquivos**
ansible all -i hosts -m copy -a "src=./copy.txt dest=/copy.txt" -b

**Reiniciar**
ansible all -i hosts -m reboot -b 

ansible all -i hosts -m apt -a "name=nginx update_cache=yes" -b

**Remove pacote**
ansible all -i hosts -m apt -a "name=curl state=absent"

**Instala pacotes**
ansible all -i hosts -m apt -a "name=curl state=present"

**Parar Services**
ansible all -i hosts -m service -a "name=nginx state=stopped"

**Configurar chave ssh com senha**
ssh-agent bash
ssh-add "caminho da chave"

---------------

ansible-playbook -i hosts playbook.yml -b 

**Verbose**
Para ver quais tarefas estão sendo executadas durante a execução de um playbook ou comando Ansible, você pode usar a opção -v ou --verbose. 

Isso fornecerá informações mais detalhadas durante a execução.

Aqui estão algumas opções que você pode usar:
-v ou --verbose: Exibe informações verbosas durante a execução. 
-vvv: Exibe informações de depuração. Essa opção é útil para depurar problemas ou verificar detalhes específicos durante a execução.
-vvvv: Exibe informações de depuração mais detalhadas. Isso pode ser útil para depurar problemas complexos ou obter um registro detalhado das operações executadas.
