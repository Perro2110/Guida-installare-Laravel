# Guida all'installazione di Laravel su Linux

Questa guida ti mostrerà come installare tutto il necessario per sviluppare con Laravel su un sistema Linux.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti strumenti installati sul tuo sistema:

- PHP (versione 7.4 o superiore)
- Composer
- Node.js e npm

## Passo 0/1: Installare i prerequisiti
### Apache2
```
sudo apt install apache2
```
### MySQL
```
sudo apt install mysql-server
```

### Php
```
sudo apt install php-pear php-fpm php-dev php-zip php-curl php-xmlrpc php-gd php-mysql php-mbstring php-xml libapache2-mod-php
```

### Restart Server 
per aggiornare la config:
```
sudo service apache2 restart
```
### Check Apache

Aprendo il web browser e accedendo al seguente url: http://localhost/. 
Dovreste visualizzare un messaggio in cui dice che funziona.

### Check Php

Eseguendo il seguente comando viene svolto il controllo di funzionamento :
```
php -r 'echo "\n\n Your PHP installation is working fine. \n\n";'
```


Verifica l'installazione:

```bash
php -v
```

## Passo 2: Installare Composer

```bash
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
```

Verifica l'installazione:

```bash
composer --version
```

## Passo 3: Installare Node.js e npm

```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt install -y nodejs
```

Verifica l'installazione:

```bash
node -v
npm -v
```

## Passo 4: Installare Laravel

Ora che abbiamo tutti i prerequisiti, possiamo installare Laravel:

```bash
composer global require laravel/installer
```

Aggiungi il percorso di Composer al tuo PATH. Aggiungi questa linea al tuo file `.bashrc` o `.zshrc`:

```bash
export PATH="$PATH:$HOME/.composer/vendor/bin"
```

Ricarica il file di configurazione della shell:

```bash
source ~/.bashrc  # o source ~/.zshrc se usi Zsh
```

## Passo 5: Creare un nuovo progetto Laravel

Per creare un nuovo progetto Laravel, esegui:

```bash
laravel new nome-progetto
```

Oppure, se preferisci usare Composer direttamente:

```bash
composer create-project --prefer-dist laravel/laravel nome-progetto
```

## Passo 6: Avviare il server di sviluppo

Naviga nella directory del tuo progetto e avvia il server di sviluppo:

```bash
cd nome-progetto
php artisan serve
```

Ora puoi accedere alla tua applicazione Laravel all'indirizzo `http://localhost:8000`.

---

In caso di progetto gia esistente entrare nella cartela di tale progetto da terminale,
a seguire

```bash
composer install 
```
```bash
cp .env.example .env 
```
```bash
php artisan key:generate
```
modificare credenziali in file .env inserendo nome utente e password di Db

```bash
php artisan migrate 
```


## Conclusione

Hai installato con successo Laravel e tutti gli strumenti necessari per lo sviluppo su Linux. Buon coding!
