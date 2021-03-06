# Derive Events using rules

Given an log path and, set of rules, they are channelised to event derivation algorithm. Event derivation algorithm is responsible for building the transformed log. Evaluation metrics and log statistics for both, original log and transformed log are caomputed and returned.

Call apply_trans(logpath, activities, attributes, predicates, thresholds, location, new_activities, window, order_flag, visual_flag)
It takes as input
	
        1. logpath (str): Path of event log
        2. activities (List of str): List of activities in rule
        3. attributes (List of str): List of attributes in rule
        4. predicates (List of str): List of predicates in rule
        5. thresholds (List of float or str): List of thresholds in rule
        6. location (List of str): List of locations for derived events in rule
        7. new_activities (List of str): List of derived event's identifiers
        8. window (List of int): List of time windows in rule
        9. order_flag (bool): Flag to denote if order of events in log is considered
        10.visual_flag (bool): Flag to denote if activities in rule should be retained

The resulting transformed event log can be found in the same location as that of original log with same name suffixed with "modified" keyword.

## Installation

```pip install derive_event_pm4py```

## How to use it?

Install derive_event_pm4py package. Following, from derive_event import apply_trans.

        Example: 
        path = "<path>\<file>.xes"
        act = [["E", "F"], ["E", "G"], ["E", "H"]]
        attr = [["additional", "additional"], ["additional", "additional"], ["additional", "additional"]]
        pred = [["LT", "LT"], ["LT", "GT"], ["LT", "GT"]]
        thres = [[100, 50], [100, 40], [100, 50]]
        loc = ["end", "end", "end"]
        new_act = ["EF", "EG", "EH"]
        window = [432000, 432000, 432000]
        order = [False, False, False]
        visual = False
        apply_trans(path, act, attr, pred, thres, loc, new_act, window, order, visual)

## License

Copyright (c) 2020 Ajay Pandi

This repository is licensed under the MIT license. See LICENSE for details.