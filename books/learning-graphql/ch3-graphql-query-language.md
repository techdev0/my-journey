Combining queries in one query document:
```
query liftsAndTrails {
  open: liftCount(status: OPEN)
  chairlifts: allLifts {
    liftName: name
    status
  }
  skiSlopes: allTrails {
    name
    difficulty
  }
}
```

Fragments
1. Selection sets that can be reused in multiple operations
```
fragment liftInfo on Lift {
  name
  status
  capacity
  night
  elevationGain
}
```
