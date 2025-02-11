# El meu repositori de M4

Activitat de programador de tasques
Gestión de LDAP
Crear una unidad organizativa
bash
Copiar
Editar
ldapadd -x -D "cn=admin,dc=example,dc=com" -W -f ou-jetagache.ldif
slapcat | grep "ou=Jet-Agache"
Añadir usuarios con un archivo LDIF
bash
Copiar
Editar
ldapadd -x -D "cn=admin,dc=example,dc=com" -W -f users.ldif
slapcat | grep "uid="
Buscar usuarios de una ubicación específica
bash
Copiar
Editar
ldapsearch -x -b "ou=Jet-Agache,dc=example,dc=com" "(localityName=SpecificLocation)"
Eliminar un usuario en LDAP
bash
Copiar
Editar
ldapdelete -x -D "cn=admin,dc=example,dc=com" -W "uid=user1,ou=Jet-Agache,dc=example,dc=com"
Administración de usuarios
Crear un usuario administrador
bash
Copiar
Editar
sudo adduser newadmin
sudo usermod -aG sudo newadmin
Configurar una fecha de expiración para un usuario
bash
Copiar
Editar
sudo chage -E 2025-03-11 username
Eliminar un usuario
bash
Copiar
Editar
sudo userdel -r username
Monitorización del sistema
Mostrar espacio disponible en /home
bash
Copiar
Editar
df -h /home
Consultar particiones del disco
bash
Copiar
Editar
fdisk -l
Automatización de tareas
Programar reinicios con cron
bash
Copiar
Editar
sudo crontab -e
# Ejemplo: reiniciar lunes y viernes a las 20:00
0 20 * * 1,5 /sbin/shutdown -r now
Extras
Hacer backup de LDAP
bash
Copiar
Editar
slapcat > ldap-backup-$(date +%F).ldif
Cambiar el shell de un usuario
bash
Copiar
Editar
sudo chsh -s /bin/zsh username
Montar un disco manual
bash
Copiar
Editar
sudo mount /dev/sdX1 /mnt/directory
