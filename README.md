AWS CLOUD
1. primeramente he creado tres máquinas EC2, una master, webserver y database
2. me conecté a la máquina máster para instalar python mediante los comandos
  - curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
  - python3 get-pip.py --user
3. instalación de ansible con 
  - pip python3 -m pip install --user ansible
4. generé una clave ssh con comando ssh-keygen -t rsa en el master
  - entrando en el directorio cat /root/.ssh/id_rsa.pub copié la clave para llevar a las máquinas webserver y database
5. en cada una de las máquinas se ha copiado la clave en 
  - vi /root/.ssh/authorized_keys
6. Una vez copiado ya se pudo comprobar la conexión desde el máster al las dos máquinas mediante
  - ssh <ip de la máquina>
7. Luego en la master se crea los ficheros playbooks
  - ping.yml  // nano ping.yaml
  - inventory.ini  //nano inventory.ini
  - install.yml // nano install.yml
8. Primeramente se hace el ping mediante y después se instala los recursos
  - ansible all -i inventory.ini -m ping

    
  - ansible-playbook install.yml
Conclusión:
Todo a funcionado perfectamente sin problemas algún, vale resaltar que todo se hizo en AWS.
