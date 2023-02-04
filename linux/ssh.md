# How to: Configure SSH-Agent forwarding
(1) Client: Set ForwardAgent to yes  
vi /etc/ssh/ssh_config  
--> ForwardAgent yes  

// ssh agent aktivieren  
eval `ssh-agent -s`  
  
// priv key hinzufügen  
ssh-add id_rsa  (bzw. ssh-add <path/to/priv_key>)  

(2) Server: Set AllowAgentForwarding to yes  
vi /etc/ssh/sshd_config  
--> AllowAgentForwarding yes  

(3) Test  
ssh -i id_rsa /<bastion-user/>@/bastion-ip>  
ssh /<internal-host/>  

https://www.ssh.com/academy/ssh/agent