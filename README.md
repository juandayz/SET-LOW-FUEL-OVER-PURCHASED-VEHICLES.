# SET-LOW FUEL-AMOUNT-OVER-PURCHASED-VEHICLES.

1.In server_publishVehicle2.sqf Find:

PASTE:
```ruby
 _object setfuel _fuel;
```
BELOW OF:
```ruby
	clearWeaponCargoGlobal  _object;
	clearMagazineCargoGlobal  _object;
	dayz_serverObjectMonitor set [count dayz_serverObjectMonitor,_object];
	_object setVariable ["ObjectID", _oid, true];
	_object setVariable ["lastUpdate",diag_tickTime];
	_object setVariable ["CharacterID", _characterID, true];
```

