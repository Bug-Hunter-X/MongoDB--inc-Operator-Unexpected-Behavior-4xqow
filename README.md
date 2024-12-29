# MongoDB $inc Operator Unexpected Behavior
This repository demonstrates an uncommon bug related to the `$inc` operator in MongoDB.  The `$inc` operator, when used incorrectly with a negative value and a non-existent field, can lead to unexpected results or errors.

## Bug Description
The primary issue lies in how `$inc` interacts with fields that do not exist. While it typically increments an existing numeric field, if the field is absent, the behavior is not entirely intuitive.

## Solution
The provided solution addresses this by first checking for the field's existence using the `$setOnInsert` operator within the `$inc` operation. If the field doesn't exist, it will create the field and insert the negative value accordingly.