
# jc.parsers.date
jc - JSON CLI output utility `date` command output parser

Usage (cli):

    $ date | jc --date

    or

    $ jc date

Usage (module):

    import jc.parsers.date
    result = jc.parsers.date.parse(date_command_output)

Compatibility:

    'linux', 'darwin', 'freebsd'

Examples:

    $ date | jc --date -p
    {
      "year": 2020,
      "month_num": 7,
      "day": 31,
      "hour": 16,
      "minute": 48,
      "second": 11,
      "month": "Jul",
      "weekday": "Fri",
      "weekday_num": 6,
      "timezone": "PDT"
    }

    $ date | jc --date -p -r
    {
      "year": "2020",
      "month": "Jul",
      "day": "31",
      "weekday": "Fri",
      "hour": "16",
      "minute": "50",
      "second": "01",
      "timezone": "PDT"
    }


## info
```python
info()
```


## process
```python
process(proc_data)
```

Final processing to conform to the schema.

Parameters:

    proc_data:   (dictionary) raw structured data to process

Returns:

    Dictionary. Structured data with the following schema:

    {
      "year":         integer,
      "month_num":    integer,
      "day":          integer,
      "hour":         integer,
      "minute":       integer,
      "second":       integer,
      "month":        string,
      "weekday":      string,
      "weekday_num":  integer,
      "timezone":     string
    }


## parse
```python
parse(data, raw=False, quiet=False)
```

Main text parsing function

Parameters:

    data:        (string)  text data to parse
    raw:         (boolean) output preprocessed JSON if True
    quiet:       (boolean) suppress warning messages if True

Returns:

    Dictionary. Raw or processed structured data.

