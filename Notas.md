# Bandit Level Notes

---

## Niveles de Bandit

### **pass1**
- **Contraseña**: `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`
- **Comandos**: 
  - `ls`
  - `cat`
  
### **pass2**
- **Contraseña**: `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`
- **Comando**: 
  - `cat ./-`

### **pass3**
- **Contraseña**: `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`
- **Comando**: 
  - `cat " "`

### **pass4**
- **Contraseña**: `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`
- **Comandos**: 
  - `ls -al`
  - `cat ...oculto`

### **pass5**
- **Contraseña**: `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`
- **Comando**:
  - `file inhere/* - find . -name -file07 | xargs cat`

### **pass6**
- **Contraseña**: `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`
- **Comando**: 
  - `find . -type f -readable ! -executable -size 1033c | xargs cat`

### **pass7**
- **Contraseña**: `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`
- **Comando**: 
  - `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null | xargs cat`

### **pass8**
- **Contraseña**: `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`
- **Comandos**: 
  - `cat data.txt | wc -l` (para contar las líneas)
  - `grep "millionth" data.txt`

### **pass9**
- **Contraseña**: `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`
- **Comando**:
  - `cat data.txt | sort | uniq -u`

### **pass10**
- **Contraseña**: `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`
- **Comando**: 
  - `strings data.txt | grep "==="`

### **pass11**
- **Contraseña**: `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`
- **Comando**: 
  - `cat data.txt | base64 -d`

### **pass12**
- **Contraseña**: `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`
- **Comandos**: 
  - `cat data.txt | tr "G-ZA-Fg-za-f" "T-ZA-St-za-s"`

### **pass13**
- **Contraseña**: `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`
- **Comandos**:
  - `xxd -r data.hex > data`
  - `file data`
  - `mv data data.gzip`
  - `7z l data.gzip`
  - `7z x data.gzip`
  - Creamos el script `decompressor.sh`, le damos permisos de ejecución con `chmod +x`.
  - Eliminamos el archivo `data.bin` y movemos `data.gzip` a `content.gzip`.
  - El script se encuentra al final de las notas.

### **pass14**
- **Contraseña**: `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`
- **Comando**: 
  - `ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220`
  - `cat /etc/bandit_pass/bandit14`

### **pass15**
- **Contraseña**: `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`
- **Comando**:
  - `echo 'MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS' | nc localhost 30000`
  - Alternativamente: `telnet localhost 30000`
  - Colocar la contraseña `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`.

### **pass16**
- **Contraseña**: `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx`
- **Comando**:
  - `openssl s_client -connect localhost:30001`
  - Se le pasa la contraseña `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx`.

### **pass17**
- **Contraseña**: `EReVavePLFHtFlFsjn3hyzMlvSuSAcRD`
- **Comandos**:
  - `nmap --open -T5 -v -n -p31000-32000 localhost:31790 -quiet`
  - Copiar la private key. Crear un archivo temporal:
    ```bash
    mktemp -d
    cd /tmp/tmp.ljEyl6kv1M
    nano id_rsa
    ```
    Pegar la private key y cambiar los permisos:
    ```bash
    chmod 600 id_rsa
    ```
  - Conectar por SSH:
    ```bash
    ssh -i id_rsa bandit17@bandit.labs.overthewire.org -p 2220
    ```
  - `cat /etc/bandit_pass_bandit17`

### **pass18**
- **Contraseña**: `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`
- **Comando**:
  - `diff passwords.old passwords.new`

### **pass19**
- **Contraseña**: `cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`
- **Comandos**:
  - `ssh bandit18@bandit.labs.overthewire.org -p 2220 bash`
  - `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`
  - `whoami`
  - `ls`
  - `cat readme`

### **pass20**
- **Contraseña**: `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`
- **Comando**:
  - `./bandit20-do bash -p`

### **pass21**
- **Contraseña**: `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`
- **Comandos**:
  - Conectarse a `bandit20` por bash y abrir un puerto para escuchar:
    ```bash
    nc -nlvp 6000
    ```
  - Conectarse a `bandit20` en otra terminal y ejecutar:
    ```bash
    ./suconnect 6000
    ```
  - En la terminal donde se escucha, pegar la contraseña `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`.

### **pass22**
- **Contraseña**: `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`
- **Comandos**:
  - `ls -l /etc/cron.d`
  - `cat /etc/cron.d/cronjob_bandit22`
  - `cat /usr/bin/cronjob_bandit22.sh`
  - `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

### **pass23**
- **Contraseña**: `0Zf11ioIjMVN551jX3CmStKLYqjk54Ga`
- **Comandos**:
  - `ls -l /etc/cron.d`
  - `cat /etc/cron.d/cronjob_bandit23`
  - `cat /usr/bin/cronjob_bandit23.sh`
  - `echo I am user bandit23 | md5sum | cut -d ' ' -f 1`
  - Hacer un `cat` al hash de la salida del comando anterior.

### **pass24**
- **Contraseña**: `gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8`
- **Comandos**:
  - `mktemp -d`
  - `cd /tmp/tmp.ljEyl6kv1M`
  - Crear un script `script.sh

### **pass25**
- **Contraseña**: `iCi86ttT4KSNe1armKiwbQNmB3YJP3q4`
- **Comandos**:
  - `mktemp -d`
  - `cd /tmp/tmp.ljEyl6kv1M`
  - Crear un script `script.sh` con:
    ```bash
    #! /bin/bash
    for i in {0000..9999}; do
      echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i
    done
    ```
  - Cambiar permisos:
    ```bash
    chmod +x script.sh
    ```
  - Ejecutar el script:
    ```bash
    ./script.sh > password.txt
    ```
  - Ver el contenido de `password.txt` y pasarlo por `nc`:
    ```bash
    cat password.txt | nc localhost 30002 | grep -v -E "Wrong|Please"
    ```

### **pass26**
- **Contraseña**: `s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ`
- **Comandos**:
  - `cat /etc/passwd | grep bandit26`
  - `cat /usr/bin/showtext`
  - Para acceder a una bash, intentar con `vim`:
    ```bash
    v
    :e /etc/bandit_pass/bandit26
    :set shell=/bin/bash
    :shell
    ```

### **pass27**
- **Contraseña**: `upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB`
- **Comandos**:
  - `ls -l`
  - Ejecutar:
    ```bash
    ./bandit27-do
    ./bandit27-do bash -p
    ```
  - Ver quién está logueado:
    ```bash
    whoami
    ```
  - Obtener la contraseña:
    ```bash
    cat /etc/bandit_pass/bandit27
    ```

### **pass28**
- **Contraseña**: `Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN`
- **Comandos**:
  - `mktemp -d`
  - `cd /tmp/tmp.ljEyl6kv1M`
  - Clonar el repositorio Git:
    ```bash
    git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
    ```
  - Ver el contenido del repositorio:
    ```bash
    cd repo
    cat README
    ```

### **pass29**
- **Contraseña**: `4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7`
- **Comandos**:
  - `mktemp -d`
  - `cd /tmp/tmp.ljEyl6kv1M`
  - Clonar el repositorio Git:
    ```bash
    git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
    ```
  - Ver el contenido del repositorio:
    ```bash
    cd repo
    cat README.md
    ```
  - Ver el historial de Git:
    ```bash
    git log -p
    ```

### **pass30**
- **Contraseña**: `qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL`
- **Comandos**:
  - `mktemp -d`
  - `cd /tmp/tmp.ljEyl6kv1M`
  - Clonar el repositorio Git:
    ```bash
    git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
    ```
  - Ver el contenido del repositorio:
    ```bash
    cd repo
    cat README.md
    ```
  - Revisar las ramas de Git:
    ```bash
    git branch -r
    git checkout dev
    git lg -p
    ```

### **pass31**
- **Contraseña**: `fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy`
- **Comandos**:
  - `mktemp -d`
  - `cd /tmp/tmp.ljEyl6kv1M`
  - Clonar el repositorio Git:
    ```bash
    git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
    ```
  - Ver el contenido del repositorio:
    ```bash
    cd repo
    cat README.md
    ```
  - Ver las etiquetas de Git:
    ```bash
    git tag
    ```
  - Ver el contenido de una etiqueta específica:
    ```bash
    git show secret
    ```

### **pass32**
- **Contraseña**: `3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K`
- **Comandos**:
  - `mktemp -d`
  - `cd /tmp/tmp.ljEyl6kv1M`
  - Clonar el repositorio Git:
    ```bash
    git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
    ```
  - Ver el contenido del repositorio:
    ```bash
    cd repo
    cat README.md
    ```
  - Crear un archivo `key.txt` con:
    ```bash
    touch key.txt
    echo "May I com in" > key.txt
    ```
  - Remover el archivo `.gitignore`:
    ```bash
    rm .gitignore
    ```
  - Añadir y hacer commit de los cambios:
    ```bash
    git add key.txt
    git commit -m "Agregando nueva clave"
    git push -u origin master
    ```

### **pass33**
- **Contraseña**: `tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0`
- **Comandos**:
  - Ejecutar `$0` para ejecutar el script actual.
  - Ver quién está logueado:
    ```bash
    whoami
    ```
  - Obtener la contraseña:
    ```bash
    cat /etc/bandit_pass/bandit33
    ```

### **pass34**
- **Contraseña**: ¡Felicidades! Has completado el último nivel del juego.
  - En este momento, no hay más niveles disponibles.
  - El equipo de OverTheWire está trabajando constantemente en nuevos niveles, así que mantén un ojo en los canales de comunicación para saber cuándo se agregarán nuevos niveles.

---

## Notas adicionales

- **Código de estado**: Se puede verificar el código de estado de un comando con `$?`.
- **Conexión SSH**: Para conectarte a los diferentes niveles usando SSH, el comando general es:
  ```bash
  ssh banditXX@bandit.labs.overthewire.org -p 2220
- **El comando `$0` en la terminal, mostrará el nombre del shell o el comando que se está ejecutando**
- **Posible script para descomprimir los archivos multiples veces comprimidos en el  nivel 13**
  
  ```bash
  #! /bin/bash

name_decompressed=$(7z l content.gzip | grep "Name" -A 2 | tail -n1 | awk 'NF{print $NF}')
7z x content.gzip > /dev/null 2>&1

while true; do
	7z l $name_decompressed > /dev/null 2>&1
	if [ "$(echo $?)" == "0" ]; then
			decompressed_next=$(7z l $name_decompressed | grep "Name" -A 2 | tail -n1 | awk 'NF{print $NF}')
			7z x $name_decompressed > /dev/null 2>&1 && name_decompressed=$decompressed_next
	else
			cat $name_decompressed; rm data* 2>/dev/null
			exit 1
	fi
done
```
