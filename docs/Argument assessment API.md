# Built-in argument assessments reference

* [Is.NotNull](#IsNotNull) ,,1.0.0,,
* [Is.NotNullOrEmpty](#IsNotNullOrEmpty) ,,1.0.0,,
* [Is.NotNullOrWhiteSpace](#IsNotNullOrWhiteSpace) ,,1.0.0,,
* [Has.NoNulls](#HasNoNulls) ^^new^^
* [Has.NoDuplicates](#HasNoDuplicates) ^^new^^
* [Has.LengthEqualTo](#HasLengthEqualTo) ^^new^^
* [Has.LengthLessThan](#HasLengthLessThan) ^^new^^
* [Has.LengthGreaterThan](#HasLengthGreaterThan) ^^new^^
* [Has.LengthLessThanOrEqualTo](#HasLengthLessThanOrEqualTo) ^^new^^
* [Has.LengthGreaterThanOrEqualTo](#HasLengthGreaterThanOrEqualTo) ^^new^^

## {anchor:IsNotNull}Is.NotNull
**Purpose**: to validate reference type argument against null.
**Applicable to**: any reference type
**Exception types**:
* **ArgumentNullException** when argument value is null.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void IsNotNullExample(object arg)
{
    Guard.Argument(() => arg, Is.NotNull /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void IsNotNullExample(object arg)
{
    Guard.Argument(() => arg, Is.NotNull, "Provided arg should not be null");
    // ...
}
{code:c#}

## {anchor:IsNotNullOrEmpty}Is.NotNullOrEmpty
**Purpose**: to validate string argument against null and empty value.
**Applicable to**: string
**Exception types**:
* **ArgumentNullException** when argument value is null.
* **ArgumentOutOfRangeException** when argument value is empty.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void IsNotNullOrEmptyExample(string arg)
{
    Guard.Argument(() => arg, Is.NotNullOrEmpty /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void IsNotNullOrEmptyExample(string arg)
{
    Guard.Argument(() => arg, Is.NotNullOrEmpty, "Provided arg should not be null or empty");
    // ...
}
{code:c#}

## {anchor:IsNotNullOrWhiteSpace}Is.NotNullOrWhiteSpace
**Purpose**: to validate string argument against null, empty and white space values.
**Applicable to**: string
**Exception types**:
* **ArgumentNullException** when argument value is null.
* **ArgumentOutOfRangeException** when argument value is empty or white space.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void IsNotNullOrWhiteSpaceExample(string arg)
{
    Guard.Argument(() => arg, Is.NotNullOrWhiteSpace /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void IsNotNullOrWhiteSpaceExample(string arg)
{
    Guard.Argument(() => arg, Is.NotNullOrWhiteSpace, "Provided arg should not be null, empty or white space");
    // ...
}
{code:c#}

## {anchor:HasNoNulls}Has.NoNulls
**Purpose**: to validate enumeration argument against null entries.
**Applicable to**: IEnumerable of references
**Exception types**:
* **ArgumentException** on first null occurence in enumeration.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void HasNoNullsExample(string[]() args)
{
    Guard.Argument(() => args, Has.NoNulls /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void HasNoNullsExample(string[]() args)
{
    Guard.Argument(() => args, Has.NoNulls, "Provided arg should not contain null");
    // ...
}
{code:c#}

## {anchor:HasNoDuplicates}Has.NoDuplicates
**Purpose**: to validate enumeration argument against duplicate entries.
**Applicable to**: IEnumerable
**Exception types**:
* **ArgumentException** on first duplicate occurence in enumeration.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void HasNoDuplicatesExample(string[]() args)
{
    Guard.Argument(() => args, Has.NoDuplicates /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void HasNoDuplicatesExample(string[]() args)
{
    Guard.Argument(() => args, Has.NoDuplicates, "Provided arg should not contain duplicate entries");
    // ...
}
{code:c#}

## {anchor:HasLengthEqualTo}Has.LengthEqualTo
**Purpose**: to validate array length equal to particular value.
**Applicable to**: array
**Exception types**:
* **ArgumentException** length not equal to particular value.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void HasLengthEqualToExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthEqualTo(() => 3) /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void HasLengthEqualToExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthEqualTo(() => 3), "Provided array must contain exactly 3 items");
    // ...
}
{code:c#}

## {anchor:HasLengthLessThan}Has.LengthLessThan
**Purpose**: to validate array length less than particular value.
**Applicable to**: array
**Exception types**:
* **ArgumentException** length is greater than or equal to particular value.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void HasLengthLessThanExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthLessThan(() => 3) /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void HasLengthLessThanExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthLessThan(() => 3), "Provided array length is greater than 2");
    // ...
}
{code:c#}

## {anchor:HasLengthGreaterThan}Has.LengthGreaterThan
**Purpose**: to validate array length greater than particular value.
**Applicable to**: array
**Exception types**:
* **ArgumentException** length is less than or equal to particular value.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void HasLengthGreaterThanExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthGreaterThan(() => 3) /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void HasLengthGreaterThanExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthGreaterThan(() => 3), "Provided array length is less than 4");
    // ...
}
{code:c#}

## {anchor:HasLengthLessThanOrEqualTo}Has.LengthLessThanOrEqualTo
**Purpose**: to validate array length less than or equal to particular value.
**Applicable to**: array
**Exception types**:
* **ArgumentException** length is greater than particular value.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void HasLengthLessThanOrEqualToExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthLessThanOrEqualTo(() => 3) /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void HasLengthLessThanOrEqualToExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthLessThanOrEqualTo(() => 3), "Provided array length is greater than 3");
    // ...
}
{code:c#}

## {anchor:HasLengthGreaterThanOrEqualTo}Has.LengthGreaterThanOrEqualTo
**Purpose**: to validate array length greater than or equal to particular value.
**Applicable to**: array
**Exception types**:
* **ArgumentException** length is less than particular value.
**Examples**
* This assessment can be used in a fluent syntax
{code:c#}
public static void HasLengthGreaterThanOrEqualToExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthGreaterThanOrEqualTo(() => 3) /**, ... Any other assessment **/);
    // ...
}
{code:c#}
* This assessment can be used in a dedicated syntax with particular error message
{code:c#}
public static void HasLengthGreaterThanOrEqualToExample(string[]() args)
{
    Guard.Argument(() => args, Has.LengthGreaterThanOrEqualTo(() => 3), "Provided array length is less than 3");
    // ...
}
{code:c#}