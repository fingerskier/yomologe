# yomologe
Chronologizer.


# Schema
```
_event = {
  ID: 1,
  name: '',
  startDay: 0.0,
  duration: 0.0,
  endDay: 0.0,
  predecessor_ID: 0,
  predecessorOffset: 0.0,
  successor_ID: 0,
  successorOffset: 0.0
}
```

Every event has a unique ID.
__Name__ is incidental.
Days are Julian dates in decimal form:
- 0.0 = noon on January 1, 4713BC
- Hence, if sub-day accuracy is needed, midnight[morn] is N - 0.5, midnight[morn] is N + 0.5
- Obviously: the logician needs to adjust start, duration, or end values based on which changed last
If predecessor or sucessor ID is < 1 then there is none.
A predecessive offset indicates the number of days from the startDay to the endDay of the predecessor.
A successive offset indicates the number of days from the endDay to the startDay of the successor.
