shotty python api
===========================================================

Installation
------------

Installation using pip::

    pip install shotty

Usage
-----

*Usage instructions here*

```python
from shotty import api
shotty = api('localhost', '54342a78-e2e8f65f-8040ae5f-5a01fe75-66909b98')
```

```python
shotty.get('users') # get all users
shotty.get('users', id='785845fjdfg930459') # get one user
```

```python
shotty.get('projects') # get all projects
p = shotty.get('projects', id='CASINO') # get one project
print p['paths']['root']
```

```python
shotty.get('shots', id='54342a78-e2e8f65f-8040ae5f') # get one shot
shots = shotty.get('shots', projectId='CASINO') # get all shots for test project
print len(shots)
print 'shots with client status', len([shot for shot in shots if shot['status'] == 'client'])

```

```python
shotty.get('versions', id='54342a78-e2e8f65f-8040ae5f') # get one version
versions = shotty.get('versions', projectId='CASINO') # get all versions for test project
print 'dailies versions', len([version for version in versions if version['type'] == 'dailies'])
shotty.get('versions', shotId='748324hfsd904') # get all versions for one shot
```

```python
shotty.create('shots', {'projectId': 'demo', 'sequence': 'api', 'code': '002', 'creatorId': None}) # create shot
shotty.edit('shots', {'id': 'b314aa2f-e645-4174-b9f2-25dbc6761607', 'description': 'Test'}) # edit shot
shotty.delete('b314aa2f-e645-4174-b9f2-25dbc6761607') # delete shot
```