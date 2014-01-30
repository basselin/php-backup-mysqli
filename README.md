BackupMySQL extends mysqli
==========================

Ce fichier / classe PHP vous permet de créer des jeux de sauvegardes tournantes compressés de vos bases de données MySQL.
Les fichiers retournés sont au format GZip parfaitement réutilisables dans un phpMyAdmin (ou autres).

Cette méthode ne requiert aucun accès root ou administrateur à votre serveur.
Il vous suffit simplement d'avoir les droits en lecture/écriture sur la base de données et dans l'espace de stockage où vous allez enregistrer vos fichiers.


Exemple d'utilisation
---------------------

```php
new BackupMySQL(array(
	'host' => 'localhost',
	'username' => 'root',
	'passwd' => '123456',
	'dbname' => 'ma_base'
	));
```

Options
-------

| Key | Description | Type | Default |
|------|-------------|------|---------|
| `host` | Hôte du serveur MySQL | string | `ini_get('mysqli.default_host')` |
| `username` | Identifiant de connexion | string | `ini_get('mysqli.default_user')` |
| `passwd` | Mot de passe de connexion | string | `ini_get('mysqli.default_pw')` |
| `dbname` | Nom de la base | string | `''` |
| `port` | Port de connexion | string | `ini_get('mysqli.default_port')` |
| `socket` | Socket | string | `ini_get('mysqli.default_socket')` |
| `dossier` | Dossier contenant les archives GZip | string | `./` |
| `nbr_fichiers` | Nombre de sauvegardes à conserver | integer | `5` |
| `nom_fichier` | Préfix du nom des fichiers pour la sauvegarde | string | `backup` |

