# netbox-docker-deployment


need to manually update config/configuration.py file
```
CSRF_TRUSTED_ORIGINS = [
    https://YOUR_DOMAIN
]
```

should add `''` quotes like:
```
CSRF_TRUSTED_ORIGINS = [
    'https://YOUR_DOMAIN'
]
```
