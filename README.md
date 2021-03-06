# Alkivi Backup Module

This module will install and configure a cron tab to configure backup

## Usage

### Minimal server configuration

```puppet
class { alkivi_backup:
  backup_method => 'file',
  file_dir      => '/home/alkivi-backup/admin.alkivi.fr/',
  email_subject => '[backup] report from admin.alkivi.fr',
  include_dir   =>  ['/etc', '/root', '/home', '/usr/local', '/var/log'],
  exclude_dir   =>  ['/home/alkivi-backup', '/root/archive'],
  hostname      => 'admin.alkivi.fr',
}
```

### Example with ssh

```puppet
class { alkivi_backup:
  ssh_user      => 'alkivi-web',
  email_subject => '[backup] report from web.alkivi.fr',
  include_dir   =>  ['/etc', '/root', '/home', '/usr/local', '/var/log'],
  exclude_dir   =>  ['/home/alkivi-backup'],
  hostname      => 'web.alkivi.fr',
}
```



## Credits

Original executable comes from duplicity backup : http://zertrin.org/projects/duplicity-backup/

## Limitations

* This module has been tested on Debian Wheezy, Squeeze.

## License

The code is freely distributable under the terms of the LGPLv3 license.

## Contact

Need help ? contact@alkivi.fr

## Support

Please log tickets and issues at our [Github](https://github.com/alkivi-sas/)
