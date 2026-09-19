# netbox-docker-deployment


encounter syntax error:
```
netbox  | SyntaxError: invalid syntax
netbox  | Traceback (most recent call last):
netbox  |   File "/app/netbox/netbox/manage.py", line 10, in <module>
netbox  |     execute_from_command_line(sys.argv)
netbox  |   File "/lsiopy/lib/python3.12/site-packages/django/core/management/__init__.py", line 443, in execute_from_command_line
netbox  |     utility.execute()
netbox  |   File "/lsiopy/lib/python3.12/site-packages/django/core/management/__init__.py", line 383, in execute
netbox  |     settings.INSTALLED_APPS
netbox  |   File "/lsiopy/lib/python3.12/site-packages/django/conf/__init__.py", line 122, in __getattr__
netbox  |     self._setup(name)
netbox  |   File "/lsiopy/lib/python3.12/site-packages/django/conf/__init__.py", line 109, in _setup
netbox  |     self._wrapped = Settings(settings_module)
netbox  |                     ^^^^^^^^^^^^^^^^^^^^^^^^^
netbox  |   File "/lsiopy/lib/python3.12/site-packages/django/conf/__init__.py", line 251, in __init__
netbox  |     mod = importlib.import_module(self.SETTINGS_MODULE)
netbox  |           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
netbox  |   File "/usr/lib/python3.12/importlib/__init__.py", line 90, in import_module
netbox  |     return _bootstrap._gcd_import(name[level:], package, level)
netbox  |            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
netbox  |   File "<frozen importlib._bootstrap>", line 1387, in _gcd_import
netbox  |   File "<frozen importlib._bootstrap>", line 1360, in _find_and_load
netbox  |   File "<frozen importlib._bootstrap>", line 1331, in _find_and_load_unlocked
netbox  |   File "<frozen importlib._bootstrap>", line 935, in _load_unlocked
netbox  |   File "<frozen importlib._bootstrap_external>", line 999, in exec_module
netbox  |   File "<frozen importlib._bootstrap>", line 488, in _call_with_frames_removed
netbox  |   File "/app/netbox/netbox/netbox/settings.py", line 65, in <module>
netbox  |     configuration = load_configuration(
netbox  |                     ^^^^^^^^^^^^^^^^^^^
netbox  |   File "/app/netbox/netbox/netbox/settings_utils.py", line 230, in load_configuration
netbox  |     return _import_module('netbox.configuration')
netbox  |            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
netbox  |   File "/app/netbox/netbox/netbox/settings_utils.py", line 131, in _import_module
netbox  |     return importlib.import_module(name)
netbox  |            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
netbox  |   File "/usr/lib/python3.12/importlib/__init__.py", line 90, in import_module
netbox  |     return _bootstrap._gcd_import(name[level:], package, level)
netbox  |            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
netbox  |   File "<frozen importlib._bootstrap>", line 1387, in _gcd_import
netbox  |   File "<frozen importlib._bootstrap>", line 1360, in _find_and_load
netbox  |   File "<frozen importlib._bootstrap>", line 1331, in _find_and_load_unlocked
netbox  |   File "<frozen importlib._bootstrap>", line 935, in _load_unlocked
netbox  |   File "<frozen importlib._bootstrap_external>", line 995, in exec_module
netbox  |   File "<frozen importlib._bootstrap_external>", line 1133, in get_code
netbox  |   File "<frozen importlib._bootstrap_external>", line 1063, in source_to_code
netbox  |   File "<frozen importlib._bootstrap>", line 488, in _call_with_frames_removed
netbox  |   File "/app/netbox/netbox/netbox/configuration.py", line 111
netbox  |     https://YOUR_DOMAIN
netbox  |          ^
```

Solution:
nmanually update config/configuration.py file
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
