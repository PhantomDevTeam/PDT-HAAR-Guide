### Tanker init (copy-paste into tanker's init).
```
this forceSpeed 56.5888889;
```

### Game logic init (copy-paste into game logic's init).
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
