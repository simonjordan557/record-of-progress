# **C# LINQ**

## **SUMMARY METHODS**

*These are extension methods which operate on an IEnumerable and return a single value.*


#### * **MIN()**
         * *Returns the minimum value element in the source data, i.e. `int[] {1, 2, 3}` returns `1`, `string[] {"simon", "steven", "sohail"}` returns `"simon"`.*

#### * **MAX()**
         * *Returns the maximum value element in the source data, i.e. `int[] {1, 2, 3}` returns `3`, `string[] {"simon", "steven", "sohail"}` returns `"steven"`.*

#### * **SUM()**
         * *Returns the total of all the values in the source data added together, i.e. `int[] {1, 2, 3}` returns `6`, and a `string[]` would not compile.*

#### * **COUNT()**
         * *Returns the total number of elements in the source data, i.e. `int[] {1, 2, 3}` and `string[] {"simon", "steven", "sohail"}` both return `3`.*

#### * **AVERAGE()**
         * *Returns the mean average of the source data, so **SUM()** divided by **COUNT()**. `int[] {1, 2, 3}` returns `2` ( (1+2+3) / 2 = 6 )*

### **OVERLOADS**
*These methods can be overloaded with functions, i.e. **MAX()** can be passed the function `int longest = names.Max(s = s.Length);`*



## **ACCESSOR METHODS**

*These are extension methods which operate on any IEnumerable and return a single value.*


#### * **ELEMENTAT()**
         * *Returns the value at a given index. `int[] numbers = {1, 2, 3}; int result = numbers.ElementAt(1);` would return `2`.*

#### * **FIRST()**
         * *Returns the first element.*

#### * **LAST()**
         * *Returns the last element.*

#### * **SINGLE()** 
         * *Returns the only element.*

### **OVERLOADS**
*These methods can be overloaded with functions, i.e. **FIRST()** can be passed the function `int result = names.First(s => s.Length == 5)` returns the first string of length 5 in `string[] names`.*
*Alternative functions such as FirstOrDefault(), LastOrDefault(), ElementAtOrDefault() help error-handling by returning null or 0 if the data is empty. SingleOrDefault() still fails if data.Length > 1.*



## **ORDERING METHODS**

*These are extension methods which return an IEnumerable of the same length as the input IEnumerable, but sorted according to a function.*


#### * **REVERSE()**
        * *Returns an IEnumerable which is simply the input reversed.*

#### * **ORDERBY()**
        * *Order an IEnumerable according to the function i.e. `List<string> result = daysOfWeek.OrderBy(s => s.Length).ToList();` orders by ascending length of word.*

#### * **ORDERBYDESCENDING()**
        * *The same as above, but in a descending order.*

#### * **THENBY()**
        * *Provides a second sorting instruction when the first instruction returns two common results.
          *`List<string> result = daysOfWeek.OrderBy(s => s.Length).ThenBy(s => s.ElementAt(1)).ToList();` When `"monday"` and `"friday"` have the same length, `"monday"` goes first as `'o' < 'r'`.*

#### * **THENBYDESCENDING()**
        * *The same as above, but in a descending order.*



## **TESTING METHODS**

*These are extension methods which operate on an IEnumerable and return a boolean. They are checking for something, based on a function, similar to **WHERE()**. But they are checking whether true or false, without returning the value checked.*


#### * **ANY()**
        * *Returns true or false whether there are **any** entries in the source, or **any** of the source data (i.e. at least one entry) evaluates true in the test function.*
          *`bool result = dayOfWeek.Any(s => s.Contains('r'));` If any days contain r (they do) it returns true, but doesn't return the actual days, but **WHERE()** would.*

#### * **ALL()**
        * *Returns true or false whether **every** value in the source data evaluates true in the test function.*
          *`bool result = daysOfWeek.All(s => s.Last() == 'y');` If all days have y as last letter (they do) it returns true, but doesn't return the actual days.*

#### * **CONTAINS()**
        * *Returns true or false whether the IEnumerable contains the input value.*
          *`bool result = daysOfWeek.Contains("sunday");` Reutrns true, but doesn't return the string, just the boolean true.

#### * **SEQUENCEEQUAL()**
        * *Returns true if the two IEnumerables have the same values in the same order.
          *`int[] array1 = {1, 2, 3};
            int[] array2 = {3, 2, 1};
            bool result = array1.SequenceEqual(array2);`
           Would return false since the same values are in a different order, and no data would be returned either.*



## **FILTER METHODS**

*These are extension methods which operate on an IEnumerable and return another IEnumerable, containing values filtered through a function.*


#### * **WHERE()**
        * *Returns an IEnumerable containing all values from an input IEnumerable which evaluated true after being processed through a boolean function.*
          *`List<string> results = daysOfWeek.Where(s => s.Contains('r')).ToList();` would return only the days of week which contain the letter r. `(s.Contains('r')) = true;`*

#### * **SELECT()**
        * *Returns an IEnumerable of the same length of the input IEnumerable, but transformed according to a function.*
          *`List<string> results = daysOfWeek.Select(s => s.Substring(0, 3)).ToList();` would return the first 3 letters of each day.



## **SET THEORY METHODS**

*These are extension methods which operate on IEnumerables and return an IEnumerable filtered by the method.*

#### * **DISTINCT()**
        * *Returns an IEnumerable which is the input IEnmerable stripped of duplicate values.*

#### * **CONCAT()**
        * *Given two IEnumerables it concatenates them into the returned IEnumerable, leaving duplicate values in place.*

#### * **INSTERSECT()**
         * *Given two IEnumerables, returns an IEnumerable containing only values common to both inputs.*

#### * **UNION()**
        * *Given two IEnumerables, returns an IEnumerable containing all values present in either input stripped of duplicates (**CONCAT()** then **DISTINCT()**).*

#### * **EXCEPT()**
        * *Given two IEnumerables, returns an IEnumerable containing the values unique to the first input.*



## **SHORTENING METHODS**

*These are extension methods whcih operate on an IEnumereable and return an IEnumerable stripped of a set amount of data.*

#### * **SKIP()**
        * *Returns an IEnumerable missing the first x values of the input IEnumerable, x specified as the parameter.*
          *`List<string> result = daysOfWeek.Skip(1).ToList();` Returns the days of the week from `"tuesday"` onwards.*

#### * **TAKE()**
        * *Returns an IEnumerable consisting of the first x values of the input IEnumerable, x specified as the parameter.*
          *`List<string> result = daysOfWeek.Take(5).ToList();` Returns Monday to Friday only.*

#### * **SKIPWHILE()**
        * *Returns an IEnumerable missing the first values of the input IEnumerable, and only starts 'Taking' when the function evaluates true, then continues taking.*
          *`List<int> result = oneToTen.SkipWhile(i => i == 1 || i == 3).ToList();` This evaluates false on the first element, then true after, so it still takes 3, since the 'while' is deactivated.*

#### * **TAKEWHILE()**
        * *Returns an IEnumerable containing the first values of the input IEnumerable, until the function evaluates false, then stops taking and doesn't restart.
          *`list<string> results = daysOfWeek.TakeWhile(s => s.Length < 8).ToList();` returns `"monday"` and `"tuesday"` but evaluates false for `"wednesday"` and stops taking any more strings.*



## **TYPE METHODS**

*These are extension methods which operate on an IEnumerable and return an IEnumerable either filtered by, or changed to, a certain type.*

#### * **OFTYPE()**
        * *Given an IEnumerable of multiple types, returns an IEnumerable consisting of values of a particular type.*
          *`list<object> stuff = {"hello", 1, 5.5, 2.76M, 3.3f, 'c', true};
            list<string> results = stuff.OfType<string>().ToList();` Returns only the strings from the list of objects.*

#### * **CAST()**
        * *Returns an IEnumerable of the same length as the input IEnumerable, consisting of all input values cast to a different type. It will fail if any values in the input cannot cast.*



## **OTHER METHODS**

#### * **ENUMERABLE.RANGE()**
        * *Takes two integers as an input and returns an IEnumerable with each integer between and including the inputs.*

#### * **FOREACH()**
        * *The inline ForEach takes an IEnumarable and an Action (Action is a function with void return type), and performs the Action on every value in the IEnumerable.
           Functionally similar to the traditional `foreach`.*

#### * **TOLIST(), TOARRAY()**
        * *Format the IEnumerable output as a list or array for re-use, if necessary.*






