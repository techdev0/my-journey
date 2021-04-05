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
2. using the fragment in a selection set (use three dots with the fragment name):
```
query {
    Lift(id: "jazz-cat") {
      ...liftInfo
      trailAccess {
        name
        difficulty
      }
    }
    Trail(id: "river-run") {
      name
      difficulty
      accessedByLifts {
        ...liftInfo
      }
    }
}
```
3. inline fragments
    - do not have names
    - assign selection sets to specific types directly within the query
    - used to define which fields to select from a union of different types of objects
```
 query schedule {
    agenda {
    ...on Workout {
      name
      reps
    }
    ...on StudyGroup {
      name
      subject
      students
    }
  }
}
```
4. using fragments to query a union type:
```
query today {
    agenda {
    ...workout
    ...study
  }
}

fragment workout on Workout {
  name
  reps
}

fragment study on StudyGroup {
  name
  subject
  students
}
```

Mutations
1. have names
2. have selections sets that return object types/scalars
3. using query variables:
```
mutation createSong($title:String! $numberOne:Int $by:String!) {
  addSong(title:$title, numberOne:$numberOne, performerName:$by) {
    id
    title
    numberOne
  }
}
```
4. sending input data as a json object:
```
{
  "title": "No Scrubs",
  "numberOne": true,
  "by": "TLC"
}
```
