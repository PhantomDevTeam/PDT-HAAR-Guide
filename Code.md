### Tanker init (copy-paste into tanker's init).
This code goes in the tanker's init
```
this forceSpeed 56.5888889;
```

### Game logic init (copy-paste into game logic's init).
This code goes in the game logic init. If you are using a custom variable for the tanker replace "PDT_Tanker" with your variable name.
```
[] spawn {
  private _marker = createMarker ["PDT_Tanker_Marker", getPos PDT_Tanker];
  _marker setMarkerShape "ICON";
  _marker setMarkerSize [1, 1];
  "PDT_Tanker_Marker" setMarkerType "mil_end";
  "PDT_Tanker_Marker" setMarkerText "KV-44X - Tanker";
  waitUntil {
    sleep 5;
    if (alive PDT_Tanker) then {
      "PDT_Tanker_Marker" setMarkerPos (getPos PDT_Tanker);
      false
    } else {
      deleteMarker "PDT_Tanker_Marker";
      false
    };
  };
};
```

### USAF C-130 init (copy-paste into C-130 init).
Thank you Talon#6321 in the Hatchet mod Discord for editing this to make the basket look better.
```
this forceSpeed 56.5888889;
_ropeOrigins = [[-7.5, 1, 3.25]];
_baskets = [];
_vehicle = this;
{
    _basket = "vtx_aar_basket" createVehicle [0,0,0];
    _attachPos = _x vectorAdd [-.25, -20, -5.75];
    _basket setVariable ["vtx_aar_attachPos", _attachPos, true];
    _basket attachTo [_vehicle, _attachPos];
    _rope = ropeCreate [_vehicle, [-7.5, 1, 3.25], _basket, [0, 0.75, 0] , 21];
    _basket setVariable ["vtx_aar_tanker", tanker1, true];
    _basket setVariable ["vtx_aar_rope", _rope, true];
    _basket setVariable ["vtx_aar_ropeOrigin", _x, true];
    _baskets pushBack _basket;
} forEach _ropeOrigins;
_vehicle setVariable ["vtx_aar_baskets", _baskets, true];
```

### Alternate plane basic init (copy-paste into plane init).
Use this if you just want to refuel from any plane
```
this forceSpeed 56.5888889;
[this] call vtx_uh60_aar_fnc_initTanker;
```

### Set the player's vehicle fuel to half.
Paste and execute this in the debug menu.
```
(vehicle player) setFuel 0.5;
```
Or paste this in the vehicle init.
```
this setFuel 0.5;
```
