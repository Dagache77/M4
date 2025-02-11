# El meu repositori de M4

## [Activitat de programador de tasques.md]
#Gestión_de_LDAP
#Crear_una_unidad_organizativa
bash
Copiar
Editar
ldapadd -x -D "cn=admin,dc=example,dc=com" -W -f ou-jetagache.ldif
slapcat | grep "ou=Jet-Agache"
#Añadir_usuarios_con_un_archivo_LDIF
bash
Copiar
Editar
ldapadd -x -D "cn=admin,dc=example,dc=com" -W -f users.ldif
slapcat | grep "uid="
#Buscar_usuarios_de_una_ubicación_específica
bash
Copiar
Editar
ldapsearch -x -b "ou=Jet-Agache,dc=example,dc=com" "(localityName=SpecificLocation)"
#Eliminar_un_usuario_en_LDAP
bash
Copiar
Editar
ldapdelete -x -D "cn=admin,dc=example,dc=com" -W "uid=user1,ou=Jet-Agache,dc=example,dc=com"
#Administración_de_usuarios
#Crear_un_usuario_administrador
bash
Copiar
Editar
sudo adduser newadmin
sudo usermod -aG sudo newadmin
#Configurar_una_fecha_de_expiración_para_un_usuario
bash
Copiar
Editar
sudo chage -E 2025-03-11 username
#Eliminar_un_usuario
bash
Copiar
Editar
sudo userdel -r username
#Monitorización_del_sistema
#Mostrar_espacio_disponible_en_home
bash
Copiar
Editar
df -h /home
#Consultar_particiones_del_disco
bash
Copiar
Editar
fdisk -l
#Automatización_de_tareas
#Programar_reinicios_con_cron
bash
Copiar
Editar
sudo crontab -e
# Ejemplo: reiniciar lunes y viernes a las 20:00
0 20 * * 1,5 /sbin/shutdown -r now
#Extras
#Hacer_backup_de_LDAP
bash
Copiar
Editar
slapcat > ldap-backup-$(date +%F).ldif
#Cambiar_el_shell_de_un_usuario
bash
Copiar
Editar
sudo chsh -s /bin/zsh username
#Montar_un_disco_manual
bash
Copiar
Editar
sudo mount /dev/sdX1 /mnt/directory
