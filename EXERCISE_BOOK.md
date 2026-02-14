# THE EXERCISE BOOK
## 22nd Survey Division | PTE WU | Cert IV Programming | Vidimus Omnia

### How This Book Works

Every exercise is line-by-line. Each line gets three things:

| Tag | Meaning |
|-----|---------|
| **WHAT** | What to type. The actual code. |
| **WHY** | Why this line exists. What it does. Why you need it. |
| **HOW** | How the syntax works. Page reference to the workbook. |

Every exercise is **cumulative**. Exercise 5 uses concepts from 1, 2, 3, and 4. Exercise 11 uses everything. Nothing gets dropped. If you learned it, you're using it forever.

Page references point to `paged.pdf` — the paginated workbook.

---

# PART 1: C# EXERCISES

---

## EXERCISE 1 — YOUR FIRST PROGRAM
**Workbook:** Part 1B Section 1 | **Pages 21-22**
**Concepts:** `Console.WriteLine()`, `Console.ReadLine()`, `string`, `$""`, semicolons

**Your program does this:**
```
What's your fucking name?
Wu
How old are you dog?
22
Alright Wu, you're 22. Still here. Still breathing.
```

---

**LINE 1:**
```csharp
Console.WriteLine("What's your fucking name?");
```
- **WHAT:** Prints a question to the screen.
- **WHY:** You need to ask the user something before you can read their answer. Output comes before input.
- **HOW:** `Console.WriteLine()` prints text and drops to a new line. Text goes inside `""` double quotes, inside the `()`. Ends with `;` because it's a statement. Page 21.

---

**LINE 2:**
```csharp
string name = Console.ReadLine();
```
- **WHAT:** Waits for the user to type something, stores it in a text variable called `name`.
- **WHY:** `ReadLine()` catches whatever they typed. Without storing it in a variable, the input disappears into nothing and you can't use it.
- **HOW:** `string` = the type (text). `name` = the variable name (you pick it). `=` means SET (not compare — that's `==`). `Console.ReadLine()` waits for keyboard input and returns it as text. Page 21-22.

---

**LINE 3:**
```csharp
Console.WriteLine("How old are you dog?");
```
- **WHAT:** Prints the second question.
- **WHY:** Same pattern as line 1. Ask, then read.
- **HOW:** Page 21.

---

**LINE 4:**
```csharp
string age = Console.ReadLine();
```
- **WHAT:** Catches the age as text.
- **WHY:** `ReadLine()` ALWAYS returns a `string` — even if they type a number. "22" is text until you convert it. We're not converting yet.
- **HOW:** Same pattern as line 2. Different variable name. Page 21-22.

---

**LINE 5:**
```csharp
Console.WriteLine($"Alright {name}, you're {age}. Still here. Still breathing.");
```
- **WHAT:** Prints a sentence with the user's name and age embedded in it.
- **WHY:** This is the whole point — take input, do something with it, produce output.
- **HOW:** `$` before the opening `"` turns on interpolation. `{name}` gets replaced with whatever's in the `name` variable. `{age}` same. Without `$`, you'd see literal `{name}` printed like a dickhead. Page 22-23.

---

**LINE 6:**
```csharp
Console.ReadLine();
```
- **WHAT:** Holds the console window open.
- **WHY:** Without it, the window flashes and closes before you can read anything.
- **HOW:** Just waits for Enter. Not storing the result because you don't need it. Page 22.

---

**TOTAL: 6 lines. Skills unlocked: print, read, store, interpolate.**

---
---

## EXERCISE 2 — VARIABLES & DATA TYPES
**Workbook:** Part 1B Section 2 | **Pages 22-23**
**Concepts:** `string`, `int`, `double`, `bool`, `const`, `$""` with multiple variables
**Cumulative from:** Ex1 (WriteLine, ReadLine, string, interpolation)

**Your program does this:**
```
Name: Wu
Age: 22
Bank balance: 3.5
Still breathing: True
Year that won't fucking change: 2026

Status: Wu, 22, mass of $3.50 to his name, somehow alive in 2026.
```

---

**LINE 1:**
```csharp
string name = "Wu";
```
- **WHAT:** Declares a text variable with a value.
- **WHY:** You're storing data. This time you're hardcoding it instead of reading it — proving you can set values directly.
- **HOW:** `string` = type (text). `name` = variable name. `"Wu"` = the value in double quotes because it's text. `;` at the end. Page 22.

---

**LINE 2:**
```csharp
int age = 22;
```
- **WHAT:** Declares a whole number variable.
- **WHY:** `int` holds numbers with no decimal point. Age doesn't need decimals.
- **HOW:** `int` = type (whole number). No quotes — quotes make it a string. `22` is just the number, raw. Page 22.

---

**LINE 3:**
```csharp
double balance = 3.50;
```
- **WHAT:** Declares a decimal number variable.
- **WHY:** Money has cents. `int` can't hold `3.50` — it'd chop it to `3`. `double` handles decimals.
- **HOW:** `double` = type (decimal number). The `.` makes it a double. Page 22.

---

**LINE 4:**
```csharp
bool breathing = true;
```
- **WHAT:** Declares a true/false variable.
- **WHY:** Some things are yes or no. On or off. Alive or dead. `bool` holds exactly two possible values.
- **HOW:** `bool` = type (boolean). Value is `true` or `false` — **lowercase**. Python uses `True`/`False` with capitals. C# uses lowercase. Page 22.

---

**LINE 5:**
```csharp
const int year = 2026;
```
- **WHAT:** Declares a constant — a number that can never change.
- **WHY:** Some values are locked. The year this program was written doesn't change. `const` enforces that — try to reassign it later and the compiler slaps you.
- **HOW:** `const` goes before the type. `const int` = locked whole number. Must be assigned immediately. Page 22.

---

**LINES 6-10:** Print each one individually.
```csharp
Console.WriteLine($"Name: {name}");
Console.WriteLine($"Age: {age}");
Console.WriteLine($"Bank balance: {balance}");
Console.WriteLine($"Still breathing: {breathing}");
Console.WriteLine($"Year that won't fucking change: {year}");
```
- **WHAT:** Prints each variable with a label.
- **WHY:** Proves you can declare AND use each type. If you declared it wrong, this is where the compiler screams.
- **HOW:** `$""` interpolation. Each `{variable}` gets replaced with its value. Works with ALL types — string, int, double, bool. Page 22-23.

---

**LINE 11:** The big one — all variables in one sentence.
```csharp
Console.WriteLine($"\nStatus: {name}, {age}, mass of ${balance} to his name, somehow alive in {year}.");
```
- **WHAT:** One `$""` string using every variable declared in the program.
- **WHY:** Proves you can mix multiple types in one interpolated string. The `\n` adds a blank line before it.
- **HOW:** Just stack `{variable}` blocks inside one `$""` string. C# converts each type to text automatically for display. Page 22-23.

---

**LINE 12:**
```csharp
Console.ReadLine();
```

---

**TOTAL: 12 lines. Skills unlocked: all 5 core data types (string, int, double, bool, const).**

---
---

## EXERCISE 3 — OPERATORS
**Workbook:** Part 1B Section 3 | **Pages 23-24**
**Also uses:** Type conversion (Page 35)
**Concepts:** `+`, `-`, `*`, `/`, `%`, integer division, `Math.Max()`, `Math.Abs()`, `int.Parse()`
**Cumulative from:** Ex1 (ReadLine, interpolation), Ex2 (int, double types)

**Your program does this:**
```
Pick a number dickhead: 17
Pick another one: 5

17 + 5 = 22
17 - 5 = 12
17 * 5 = 85
17 / 5 = 3
17 % 5 = 2
Bigger one: 17
Absolute of -17: 17

Integer division is a lying dog. 17 / 5 ain't 3.4, it's 3.
Actual answer: 3.4
```

---

**LINE 1:**
```csharp
Console.WriteLine("Pick a number dickhead:");
```
- **WHAT:** Ask for input.
- **WHY:** Ex1 revision — ask before you read.
- **HOW:** Page 21.

---

**LINE 2:**
```csharp
int num1 = int.Parse(Console.ReadLine());
```
- **WHAT:** Read input and convert it from text to a whole number.
- **WHY:** `Console.ReadLine()` ALWAYS gives you a `string`. You can't do maths on `"17"`. `int.Parse()` unwraps the text and gives you the actual number `17`.
- **HOW:** `int.Parse()` wraps around `Console.ReadLine()`. The `ReadLine()` runs first (gets "17"), then `Parse` converts it (gets 17). Page 35.

---

**LINE 3:**
```csharp
Console.WriteLine("Pick another one:");
```

---

**LINE 4:**
```csharp
int num2 = int.Parse(Console.ReadLine());
```
- **WHAT:** Same as line 2 for the second number.

---

**LINES 5-9 — Arithmetic:**
```csharp
Console.WriteLine($"{num1} + {num2} = {num1 + num2}");
Console.WriteLine($"{num1} - {num2} = {num1 - num2}");
Console.WriteLine($"{num1} * {num2} = {num1 * num2}");
Console.WriteLine($"{num1} / {num2} = {num1 / num2}");
Console.WriteLine($"{num1} % {num2} = {num1 % num2}");
```
- **WHAT:** Prints the result of each arithmetic operation.
- **WHY:** Proves you know all 5 operators. `%` (modulo) gives the remainder — 17 % 5 = 2 because 5 goes into 17 three times with 2 left over.
- **HOW:** You can do maths INSIDE the `{}` braces in an interpolated string. `{num1 + num2}` calculates and inserts the answer. Page 23.

---

**LINE 10:**
```csharp
Console.WriteLine($"Bigger one: {Math.Max(num1, num2)}");
```
- **WHAT:** Prints whichever number is larger.
- **WHY:** `Math.Max()` is a built-in method — takes two numbers, returns the bigger one.
- **HOW:** `Math` is a toolbox (class). `.Max()` reaches inside and grabs the Max method. Page 24. The dot means "go inside this and use that" — Page 13.

---

**LINE 11:**
```csharp
Console.WriteLine($"Absolute of -{num1}: {Math.Abs(-num1)}");
```
- **WHAT:** Strips the negative sign off a number.
- **WHY:** `Math.Abs()` gives the absolute value. -17 becomes 17.
- **HOW:** Page 24.

---

**LINES 12-13 — The integer division trap:**
```csharp
Console.WriteLine($"Integer division is a lying dog. {num1} / {num2} ain't {(double)num1 / num2}, it's {num1 / num2}.");
Console.WriteLine($"Actual answer: {(double)num1 / num2}");
```
- **WHAT:** Shows that `int / int` drops decimals, and how to fix it.
- **WHY:** `17 / 5` = `3` when both are `int`. The decimal gets chopped. This catches EVERYONE. Page 24.
- **HOW:** `(double)num1` casts `num1` to a double temporarily. Now it's `double / int` which gives a `double` result: `3.4`. The cast doesn't change the original variable.

---

**LINE 14:**
```csharp
Console.ReadLine();
```

---

**TOTAL: 14 lines. Skills unlocked: arithmetic, int.Parse(), Math class, integer division trap, type casting.**

---
---

## EXERCISE 4 — ARRAYS
**Workbook:** Part 1B Section 4 | **Pages 24-25**
**Concepts:** `string[]`, `int[]`, indexing `[0]`, `.Length`, parallel arrays, `for` loop
**Cumulative from:** Ex1 (interpolation), Ex2 (int type), Ex3 (int.Parse)

**Your program does this:**
```
=== LOADOUT ===
1. Knife — 25 damage
2. Pistol — 40 damage
3. Shotgun — 80 damage
4. Sniper — 120 damage

Total weapons: 4
First weapon: Knife
Last weapon: Sniper
```

---

**LINE 1:**
```csharp
string[] weapons = { "Knife", "Pistol", "Shotgun", "Sniper" };
```
- **WHAT:** Declares an array (list) of strings with 4 items.
- **WHY:** You need to store multiple related values under one name. Each item gets a number (index) starting at `[0]`.
- **HOW:** `string[]` = "list of text". The `[]` makes it plural — `string` is one, `string[]` is many. Items inside `{ }` separated by commas. Page 24.

---

**LINE 2:**
```csharp
int[] damage = { 25, 40, 80, 120 };
```
- **WHAT:** Declares a parallel integer array.
- **WHY:** `damage[0]` matches `weapons[0]`. Knife = 25. Pistol = 40. Same index = same thing. Like two columns in a spreadsheet.
- **HOW:** `int[]` = "list of whole numbers". No quotes on the numbers. Must have the same number of items as `weapons`. Page 24-25.

---

**LINE 3:**
```csharp
Console.WriteLine("=== LOADOUT ===");
```

---

**LINES 4-7 — The for loop:**
```csharp
for (int i = 0; i < weapons.Length; i++)
{
    Console.WriteLine($"{i + 1}. {weapons[i]} — {damage[i]} damage");
}
```
- **WHAT:** Loops through every item in both arrays and prints them.
- **WHY:** Without a loop you'd write 4 separate lines. The loop handles any array size automatically.
- **HOW:** Three parts inside `for ()` — Page 25:
  - `int i = 0` — start at index 0 (first item)
  - `i < weapons.Length` — keep going while `i` is less than the count
  - `i++` — add 1 to `i` after each loop
  - `weapons[i]` grabs the item at position `i`. `damage[i]` grabs the matching damage.
  - `i + 1` in the output because humans count from 1 but arrays count from 0.
  - **NO SEMICOLON after the `for ()` line.** That kills the loop. Page 12-13.

---

**LINE 8:**
```csharp
Console.WriteLine($"\nTotal weapons: {weapons.Length}");
```
- **WHAT:** Prints how many items are in the array.
- **WHY:** `.Length` gives the count. You'll use this constantly.
- **HOW:** `.Length` is a property — no `()` after it. It's a fact, not an action. Page 25.

---

**LINE 9:**
```csharp
Console.WriteLine($"First weapon: {weapons[0]}");
```
- **WHAT:** Prints the first item.
- **WHY:** Proves arrays start at `[0]`, not `[1]`.
- **HOW:** `[0]` = first item. Always. Page 24.

---

**LINE 10:**
```csharp
Console.WriteLine($"Last weapon: {weapons[weapons.Length - 1]}");
```
- **WHAT:** Prints the last item.
- **WHY:** Array has 4 items. Last one is `[3]`, not `[4]`. `[4]` crashes with `IndexOutOfRangeException`.
- **HOW:** `Length - 1` always gives the last valid index. 4 - 1 = 3. Page 25.

---

**LINE 11:**
```csharp
Console.ReadLine();
```

---

**TOTAL: 11 lines. Skills unlocked: string[], int[], [index], .Length, parallel arrays, for loop.**

---
---

## EXERCISE 5 — LOOPS (CUMULATIVE)
**Workbook:** Part 1B Section 5 | **Pages 25-26**
**Concepts:** `for` loop (dynamic), `foreach` loop, `while` loop, `!=`
**Cumulative from:** Ex1 (ReadLine, interpolation), Ex2 (string, int), Ex3 (int.Parse), Ex4 (arrays, for loop)

---

**LINE 1:**
```csharp
Console.WriteLine("What do they call you, shithead?");
```
- **WHAT:** Ask for the user's name.
- **WHY:** Ex1 revision. Name gets used throughout the whole program.
- **HOW:** Page 21.

---

**LINE 2:**
```csharp
string name = Console.ReadLine();
```
- **WHAT:** Store the name.
- **WHY:** Ex1 revision — `string` from `ReadLine`.
- **HOW:** Page 21-22.

---

**LINE 3:**
```csharp
Console.WriteLine($"Alright {name}, how many reps can you do?");
```
- **WHAT:** Ask for a number. Uses `$""` with their name.
- **WHY:** Ex1 interpolation revision + setup for Ex3 `int.Parse`.
- **HOW:** Page 22-23.

---

**LINE 4:**
```csharp
int reps = int.Parse(Console.ReadLine());
```
- **WHAT:** Read input, convert text to number.
- **WHY:** Ex3 revision — can't do maths on text.
- **HOW:** Page 35.

---

**LINES 5-9 — for loop (Part A):**
```csharp
Console.WriteLine($"\n{name}'s rep count:");
for (int i = 1; i <= reps; i++)
{
    Console.WriteLine($"Rep {i} of {reps} — keep fucking going");
}
```
- **WHAT:** Counts from 1 to whatever number they entered.
- **WHY:** Ex4 revision BUT now the end point is a VARIABLE, not hardcoded. The loop adapts to user input. Dynamic.
- **HOW:** `i = 1` start. `i <= reps` — up to AND including their number. `i++` adds 1. Page 25.

---

**LINES 10-16 — parallel arrays + for loop (Ex4 revision):**
```csharp
string[] insults = { "Weak", "Pathetic", "Embarrassing", "Soft", "Coward" };
int[] severity = { 2, 4, 6, 8, 10 };

Console.WriteLine("\nPerformance review:");
for (int i = 0; i < insults.Length; i++)
{
    Console.WriteLine($"- {insults[i]} (severity: {severity[i]}/10)");
}
```
- **WHAT:** Two parallel arrays printed with a `for` loop.
- **WHY:** Ex4 pure revision. Keeping arrays and parallel indexing warm.
- **HOW:** `insults[i]` and `severity[i]` — same index, same item. Page 24-25.

---

**LINES 17-21 — foreach loop (NEW):**
```csharp
Console.WriteLine($"\n{name}, here's what they think of you:");
foreach (string insult in insults)
{
    Console.WriteLine($"- {insult}");
}
```
- **WHAT:** Loops through the array without a counter.
- **WHY:** NEW CONCEPT. `foreach` is simpler than `for` when you don't need the index number. You just want each item, one at a time. No `i`, no `.Length`, no `[i]`.
- **HOW:** `foreach (string insult in insults)` — read it like English: "for each string, which I'll call `insult`, in the `insults` array." The word `insult` is a temporary name you pick — it holds the current item each time through. Page 25-26.

---

**LINES 22-29 — while loop (NEW):**
```csharp
Console.WriteLine($"\n{name}, say something. Type 'quit' when you've had enough:");
string input = Console.ReadLine();
while (input != "quit")
{
    Console.WriteLine($"'{input}'? That's the best you've got? Try again:");
    input = Console.ReadLine();
}
Console.WriteLine($"Good. Fuck off then, {name}. You did {reps} reps and talked shit {insults.Length} times.");
```
- **WHAT:** Keeps asking for input until the user types "quit". Final line uses variables from the ENTIRE program.
- **WHY:** NEW CONCEPT. `while` loops run when you don't know how many iterations. Could be 1, could be 100.
- **HOW:** `while (input != "quit")` — "while input is NOT equal to quit, keep going." `!=` means not equal — Page 24. You read input BEFORE the loop (line 23) and AGAIN INSIDE the loop (line 26). Without that second `ReadLine` inside, the loop runs forever with the same value. Infinite loop. Bad. Page 26.
- The final `WriteLine` pulls `name` (line 2), `reps` (line 4), and `insults.Length` (line 10) — Ex1, Ex3, Ex4 all in one line.

---

**LINE 30:**
```csharp
Console.ReadLine();
```

---

**CUMULATIVE CHECK:**
| Concept | From | Page |
|---------|------|------|
| `Console.ReadLine()` into string | Ex1 | 21 |
| `$""` interpolation | Ex1 | 22-23 |
| `string`, `int` types | Ex2 | 22 |
| `int.Parse(Console.ReadLine())` | Ex3 | 35 |
| `string[]`, `int[]` parallel arrays | Ex4 | 24-25 |
| `for` loop with `.Length` | Ex4 | 25 |
| `foreach` loop | **NEW** | 25-26 |
| `while` loop with `!=` | **NEW** | 26 |

**TOTAL: ~30 lines. Skills unlocked: foreach, while, != operator. All previous skills reinforced.**

---
---

## EXERCISE 6 — FILE I/O (CUMULATIVE)
**Workbook:** Part 1B Section 6 | **Pages 26-27**
**Concepts:** `File.WriteAllLines()`, `File.ReadAllLines()`, `@""` literal paths
**Cumulative from:** Ex1-5 (all previous)

---

**LINE 1:**
```csharp
Console.WriteLine("What's your callsign?");
```
- **WHAT:** Ask for the user's name.
- **WHY:** Ex1 revision. Name used in file path and output.
- **HOW:** Page 21.

---

**LINE 2:**
```csharp
string callsign = Console.ReadLine();
```

---

**LINE 3:**
```csharp
string[] missions = { "Pass TAFE", "Get a job", "Get the fuck out", "Legion" };
```
- **WHAT:** Declare an array of strings.
- **WHY:** Ex4 revision — this array will be written to a file.
- **HOW:** Page 24.

---

**LINE 4:**
```csharp
string path = @"C:\Users\gwu07\Desktop\PROG\missions.txt";
```
- **WHAT:** Declares the file path as a string with `@` prefix.
- **WHY:** Backslashes in C# are escape characters. `\U` and `\P` would be interpreted as special codes. `@` tells C# to treat backslashes as literal characters.
- **HOW:** `@""` = verbatim string literal. The `@` goes OUTSIDE the quotes, right before them. Page 16, 23.

---

**LINE 5:**
```csharp
File.WriteAllLines(path, missions);
```
- **WHAT:** Writes the entire array to a text file, one item per line.
- **WHY:** This is how you save data. `WriteAllLines` takes a path and a `string[]` array and dumps each item as a line in the file. If the file doesn't exist, it creates it. If it does exist, it overwrites it.
- **HOW:** `File` is a toolbox (class). `.WriteAllLines()` reaches inside and grabs the method. Two arguments: the path, and the array. Page 26-27.

---

**LINE 6:**
```csharp
Console.WriteLine($"Missions written to {path}");
```
- **WHAT:** Confirms the write.
- **WHY:** User feedback. Don't just do shit silently.
- **HOW:** Ex1 interpolation. Page 22.

---

**LINES 7-12 — Read it back:**
```csharp
Console.WriteLine($"\n{callsign}'s mission list:");
string[] loaded = File.ReadAllLines(path);
for (int i = 0; i < loaded.Length; i++)
{
    Console.WriteLine($"{i + 1}. {loaded[i]}");
}
```
- **WHAT:** Reads the file back into a new array and prints each line with a number.
- **WHY:** Proves the file was actually written AND that you can read it back. `File.ReadAllLines()` returns a `string[]` — same type you wrote.
- **HOW:** `File.ReadAllLines(path)` reads every line of the file into a new array. Then the `for` loop (Ex4 revision) prints them. Page 26-27.

---

**LINES 13-17 — foreach (Ex5 revision):**
```csharp
Console.WriteLine($"\nSame list, foreach style:");
foreach (string mission in loaded)
{
    Console.WriteLine($"- {mission}");
}
```
- **WHAT:** Same data, printed with `foreach` instead of `for`.
- **WHY:** Ex5 revision — keeping `foreach` warm.
- **HOW:** Page 25-26.

---

**LINE 18:**
```csharp
Console.WriteLine($"\nTotal missions: {loaded.Length}. Get moving, {callsign}.");
```
- **WHAT:** Uses `.Length` and the callsign variable.
- **WHY:** Ex4 revision (`.Length`) and Ex1 revision (name variable in output).

---

**LINE 19:**
```csharp
Console.ReadLine();
```

---

**CUMULATIVE CHECK:**
| Concept | From | Page |
|---------|------|------|
| ReadLine, string, interpolation | Ex1 | 21-22 |
| string[] arrays | Ex4 | 24 |
| for loop | Ex4 | 25 |
| foreach loop | Ex5 | 25-26 |
| `File.WriteAllLines()` | **NEW** | 26-27 |
| `File.ReadAllLines()` | **NEW** | 26-27 |
| `@""` verbatim string | **NEW** | 16, 23 |

**TOTAL: ~19 lines. Skills unlocked: file read/write, @ paths. All previous skills reinforced.**

---
---

## EXERCISE 7 — TRY-CATCH (CUMULATIVE)
**Workbook:** Part 1B Section 7 | **Pages 27-29**
**Concepts:** `try { }`, `catch { }`, `FormatException`, `ex.Message`, combining with `while`
**Cumulative from:** Ex1-6 (all previous)

---

**LINE 1:**
```csharp
Console.WriteLine("Welcome to the shit calculator. What's your name?");
```
- **WHAT:** Ask for name.
- **WHY:** Ex1 revision. Used throughout.

---

**LINE 2:**
```csharp
string name = Console.ReadLine();
```

---

**LINES 3-16 — The safe number reader with while + try/catch:**
```csharp
int number = 0;
bool valid = false;

while (!valid)
{
    Console.WriteLine($"Give me a number, {name}:");
    try
    {
        number = int.Parse(Console.ReadLine());
        valid = true;
    }
    catch (FormatException)
    {
        Console.WriteLine("That's not a fucking number. Try again.");
    }
}
```
- **WHAT (line 3):** `int number = 0;` — Declares the number variable OUTSIDE the loop.
- **WHY (line 3):** Scope — Page 18-19. If you declare it inside the loop, it dies when the `}` closes and you can't use it after. Declare outside, fill inside.
- **HOW (line 3):** `= 0` gives it a default value so the compiler doesn't complain about "unassigned variable."

- **WHAT (line 4):** `bool valid = false;` — A flag that controls the loop.
- **WHY (line 4):** The `while` loop checks this flag. Once we get a valid number, we set it to `true` and the loop stops.
- **HOW (line 4):** Ex2 revision — `bool` type. Page 22.

- **WHAT (line 6):** `while (!valid)` — Loop while `valid` is NOT true.
- **WHY (line 6):** Ex5 revision — `while` loop. `!` means NOT. `!valid` = "not valid" = "valid is false." Keeps looping until we get a real number.
- **HOW (line 6):** `!` is the NOT operator. Page 11. `while` — Page 26.

- **WHAT (lines 8-12):** `try { }` wraps the risky code. `int.Parse()` might explode.
- **WHY:** If the user types "abc", `int.Parse("abc")` throws a `FormatException` and crashes the program. `try` says "attempt this, and if it explodes, don't crash — go to the `catch` instead."
- **HOW:** `try { risky code }` — Page 27-28. If nothing goes wrong, `valid = true` runs and the loop ends. If it explodes, execution jumps to `catch`.

- **WHAT (lines 13-16):** `catch (FormatException)` — Catches that specific error type.
- **WHY:** Prints a message instead of crashing. The loop continues because `valid` is still `false`.
- **HOW:** `catch` runs ONLY if `try` fails. `FormatException` is the specific error `int.Parse` throws on non-numeric input. Page 27-28.

---

**LINES 17-22 — Use the number (all previous exercises):**
```csharp
string[] operations = { "squared", "doubled", "tripled", "absolute" };
int[] results = { number * number, number * 2, number * 3, Math.Abs(number) };

Console.WriteLine($"\n{name}, here's what we can do with {number}:");
for (int i = 0; i < operations.Length; i++)
{
    Console.WriteLine($"- {number} {operations[i]} = {results[i]}");
}
```
- **WHAT:** Parallel arrays with calculated values, printed with a for loop.
- **WHY:** Ex3 revision (operators, Math.Abs), Ex4 revision (parallel arrays, for loop). Stacking everything.
- **HOW:** The `results` array is filled with EXPRESSIONS, not just raw numbers. `number * number` calculates at declaration time. Page 23-25.

---

**LINES 23-27 — File output (Ex6 revision):**
```csharp
string[] log = { $"Name: {name}", $"Number: {number}", $"Squared: {number * number}" };
File.WriteAllLines(@"C:\Users\gwu07\Desktop\PROG\calclog.txt", log);
Console.WriteLine($"\nResults saved. Get fucked, {name}.");
```
- **WHAT:** Writes results to a file.
- **WHY:** Ex6 revision — file I/O stays warm. Also shows you can use `$""` interpolation inside array declarations.
- **HOW:** Page 26-27.

---

**LINE 28:**
```csharp
Console.ReadLine();
```

---

**CUMULATIVE CHECK:**
| Concept | From | Page |
|---------|------|------|
| ReadLine, string, interpolation | Ex1 | 21-22 |
| int, bool types | Ex2 | 22 |
| int.Parse, operators, Math.Abs | Ex3 | 23-24, 35 |
| Parallel arrays, for loop | Ex4 | 24-25 |
| while loop, ! operator | Ex5 | 26 |
| File.WriteAllLines, @"" | Ex6 | 26-27, 16 |
| `try { } catch { }` | **NEW** | 27-29 |
| `FormatException` | **NEW** | 27-28 |
| Scope (declare outside loop) | **NEW** | 18-19 |

**TOTAL: ~28 lines. Skills unlocked: try/catch, exception handling, scope awareness. All previous reinforced.**

---
---

## EXERCISE 8 — STRING FORMATTING (CUMULATIVE)
**Workbook:** Part 1B Section 8 | **Page 29**
**Concepts:** `:C` currency, `:F2` fixed decimal, `{value,-width}` padding/alignment
**Cumulative from:** Ex1-7 (all previous)

---

**LINES 1-3:**
```csharp
Console.WriteLine("What's your name, soldier?");
string name = Console.ReadLine();
Console.WriteLine($"{name}'s supply run. Enter item count:");
```
- **WHAT:** Name input + prompt.
- **WHY:** Ex1 revision.

---

**LINES 4-9 — Safe number input (Ex7 revision):**
```csharp
int count = 0;
bool valid = false;
while (!valid)
{
    try
    {
        count = int.Parse(Console.ReadLine());
        valid = true;
    }
    catch (FormatException)
    {
        Console.WriteLine("Numbers only, dipshit:");
    }
}
```
- **WHAT:** Try-catch inside a while loop for safe input.
- **WHY:** Ex7 revision — this pattern never goes away.
- **HOW:** Page 27-29.

---

**LINES 10-14 — Parallel arrays with formatting:**
```csharp
string[] items = { "Ammo", "MRE", "Water", "Medkit" };
double[] prices = { 12.50, 8.99, 2.00, 45.00 };

Console.WriteLine($"\n{"ITEM",-18}{"PRICE",10}");
Console.WriteLine(new string('-', 28));
```
- **WHAT:** Prints a formatted header with padding.
- **WHY:** NEW CONCEPT. `{value,-18}` left-aligns in an 18-character wide column. `{value,10}` right-aligns in 10 characters. Makes tables look clean.
- **HOW:** Negative number = left-align. Positive = right-align. The number is the column width. Page 29. `new string('-', 28)` creates a string of 28 dashes — a divider line.

---

**LINES 15-19 — Loop with currency formatting:**
```csharp
double total = 0;
for (int i = 0; i < items.Length; i++)
{
    Console.WriteLine($"{items[i],-18}{prices[i],10:C}");
    total += prices[i];
}
```
- **WHAT:** Prints each item and price in aligned columns, with currency formatting. Accumulates a total.
- **WHY:** `:C` after the value formats it as currency ($12.50). `total += prices[i]` adds each price to the running total. Ex4 revision (arrays, for loop), Ex3 revision (operators).
- **HOW:** `{prices[i],10:C}` — right-aligned in 10 chars, formatted as currency. `:C` uses your system's currency symbol. `:F2` would give 2 decimal places without the symbol. Page 29.

---

**LINES 20-22:**
```csharp
Console.WriteLine(new string('-', 28));
Console.WriteLine($"{"TOTAL",-18}{total,10:C}");
Console.WriteLine($"\n{name} spent {total:C} on {items.Length} items. {count} of each? That's {total * count:C}. You're broke.");
```
- **WHAT:** Total line, then a summary using `name`, `total`, `items.Length`, `count`, and `total * count`.
- **WHY:** Every previous exercise concept in one output line. Name (Ex1), int variable (Ex2/3), array .Length (Ex4), currency format (new), arithmetic in interpolation (Ex3).
- **HOW:** `{total * count:C}` — does the maths AND formats as currency inside the `{}`. Page 29.

---

**LINE 23:**
```csharp
Console.ReadLine();
```

---

**CUMULATIVE CHECK:**
| Concept | From | Page |
|---------|------|------|
| ReadLine, string, interpolation | Ex1 | 21-22 |
| int, double, bool types | Ex2 | 22 |
| Operators, arithmetic in {} | Ex3 | 23-24 |
| Arrays, for loop, .Length | Ex4 | 24-25 |
| while loop | Ex5 | 26 |
| try/catch | Ex7 | 27-29 |
| `{value,-width}` padding | **NEW** | 29 |
| `:C` currency format | **NEW** | 29 |
| `:F2` fixed decimal format | **NEW** | 29 |
| `+=` accumulator | **NEW** | 23 |

**TOTAL: ~23 lines. Skills unlocked: string formatting, alignment, currency. All previous reinforced.**

---
---

## EXERCISE 9 — IF / ELSE IF / ELSE (CUMULATIVE)
**Workbook:** Part 1B Section 9 | **Pages 29-30**
**Concepts:** `if`, `else if`, `else`, `&&`, `||`, `==`, nested conditions
**Cumulative from:** Ex1-8 (all previous)

---

**LINES 1-2:**
```csharp
Console.WriteLine("What's your name, wreck?");
string name = Console.ReadLine();
```

---

**LINES 3-14 — Safe number input (Ex7 pattern):**
```csharp
Console.WriteLine("Hours of sleep last night?");
int sleep = 0;
bool valid = false;
while (!valid)
{
    try
    {
        sleep = int.Parse(Console.ReadLine());
        valid = true;
    }
    catch (FormatException)
    {
        Console.WriteLine("A number. How many hours:");
    }
}
```
- **WHAT:** Safe int input with try/catch + while.
- **WHY:** Ex7 revision. This is your standard input pattern now.

---

**LINES 15-16:**
```csharp
Console.WriteLine("Did you eat today? (yes/no)");
string food = Console.ReadLine();
```
- **WHAT:** Read a yes/no answer as a string.
- **WHY:** You need a string to compare with `==`. This sets up the `if` statement.

---

**LINES 17-27 — if / else if / else (NEW):**
```csharp
Console.WriteLine($"\n=== STATUS REPORT: {name} ===");

Console.Write("Sleep: ");
if (sleep >= 8)
{
    Console.WriteLine($"{sleep} hours — you're fine, stop complaining.");
}
else if (sleep >= 5)
{
    Console.WriteLine($"{sleep} hours — survivable. Barely.");
}
else
{
    Console.WriteLine($"{sleep} hours — you're a fucking wreck and everyone can tell.");
}
```
- **WHAT:** Checks the sleep value against multiple conditions and prints different messages.
- **WHY:** NEW CONCEPT. `if` checks a condition. If true, runs the block. If false, falls to `else if`. If that's also false, falls to `else`. Only ONE block runs. Page 29-30.
- **HOW:** `if (sleep >= 8)` — "if sleep is 8 or more." `>=` means greater than or equal to — Page 24 (comparison operators table, Page 40). `else if` is checked ONLY if the first `if` was false. `else` runs if NOTHING above was true. No condition on `else` — it's the default. `Console.Write` (no Line) keeps the cursor on the same line — Page 34.

---

**LINES 28-37 — String comparison with ==:**
```csharp
Console.Write("Food: ");
if (food == "yes")
{
    Console.WriteLine("At least you ate. Small win.");
}
else
{
    Console.WriteLine("Nothing. Running on fumes and spite.");
}
```
- **WHAT:** Compares the food string to "yes".
- **WHY:** `==` is comparison (asking). `=` is assignment (setting). Inside `if()`, you're asking a question — use `==`. Page 16.
- **HOW:** `food == "yes"` — is the value in `food` exactly equal to the text `"yes"`? Strings are case-sensitive. "Yes" != "yes". Page 16.

---

**LINES 38-48 — Combined conditions with && and ||:**
```csharp
Console.Write("Overall: ");
if (sleep >= 8 && food == "yes")
{
    Console.WriteLine($"{name}, you're actually in decent shape. Suspicious.");
}
else if (sleep < 5 && food != "yes")
{
    Console.WriteLine($"{name}, you're a disaster. But still here. Still operational.");
}
else
{
    Console.WriteLine($"{name}, mid. Could be worse. Could be better. Probably won't be.");
}
```
- **WHAT:** Multiple conditions joined with `&&` (AND) and using `!=` (NOT equal).
- **WHY:** Real decisions need multiple factors. "If sleep is good AND they ate" is different from "if sleep is shit AND they didn't eat."
- **HOW:** `&&` means AND — BOTH conditions must be true. `||` means OR — either one is enough. `!=` means NOT equal. Page 24, 30.

---

**LINES 49-51 — File log (Ex6 revision):**
```csharp
string[] log = { $"Name: {name}", $"Sleep: {sleep}", $"Food: {food}" };
File.WriteAllLines(@"C:\Users\gwu07\Desktop\PROG\statuslog.txt", log);
Console.WriteLine($"\nStatus logged. Move out, {name}.");
```
- **WHAT:** Saves the status report to a file.
- **WHY:** Ex6 revision — file I/O.
- **HOW:** Page 26-27.

---

**LINE 52:**
```csharp
Console.ReadLine();
```

---

**CUMULATIVE CHECK:**
| Concept | From | Page |
|---------|------|------|
| ReadLine, string, interpolation | Ex1 | 21-22 |
| string, int, bool types | Ex2 | 22 |
| int.Parse | Ex3 | 35 |
| while + try/catch safe input | Ex7 | 26-29 |
| File.WriteAllLines | Ex6 | 26-27 |
| `if / else if / else` | **NEW** | 29-30 |
| `==` comparison | **NEW** | 16, 30 |
| `!=` not equal | **NEW** | 24 |
| `&&` AND | **NEW** | 30 |
| `||` OR | **NEW** | 30 |
| `Console.Write` (no newline) | **NEW** | 34 |

**TOTAL: ~52 lines. Skills unlocked: branching logic, comparison operators, logical operators. All previous reinforced.**

---
---

## EXERCISE 10 — ERROR MESSAGES DECODED
**Workbook:** Part 1B Section 10 | **Pages 30-31**
**Also uses:** Appendix B Error Decoder | **Pages 133-137**
**Concepts:** Reading compiler errors, identifying common mistakes

**No code to write. Fix broken code instead.**

Each snippet below has one bug. Find it, explain WHAT's wrong, and fix it. Check your answers against the error table on Pages 133-134.

---

**BUG 1:**
```csharp
Console.WriteLine("Hello")
```
**Error:** `; expected`
**Fix:** ______________________
**Page ref:** 12-13 (semicolon rule)

---

**BUG 2:**
```csharp
int age = "twenty";
```
**Error:** `Cannot implicitly convert type 'string' to 'int'`
**Fix:** ______________________
**Page ref:** 14, 22 (types are locked)

---

**BUG 3:**
```csharp
Console.writeline("Hello");
```
**Error:** `'Console' does not contain a definition for 'writeline'`
**Fix:** ______________________
**Page ref:** 18 (C# is case-sensitive — `WriteLine` not `writeline`)

---

**BUG 4:**
```csharp
string name = "Wu";
Console.WriteLine($"Hello {Name}");
```
**Error:** `The name 'Name' does not exist in the current context`
**Fix:** ______________________
**Page ref:** 18 (case-sensitive — `name` not `Name`)

---

**BUG 5:**
```csharp
if (age = 5)
{
    Console.WriteLine("Five");
}
```
**Error:** `Cannot implicitly convert type 'int' to 'bool'`
**Fix:** ______________________
**Page ref:** 16 (`=` is SET, `==` is ASK)

---

**BUG 6:**
```csharp
for (int i = 0; i < 10; i++);
{
    Console.WriteLine(i);
}
```
**Error:** `The name 'i' does not exist in the current context`
**Fix:** ______________________
**Page ref:** 12-13, 18-19 (semicolon after `for` kills the loop; `i` dies with it)

---

**BUG 7:**
```csharp
string[] names = { "Wu", "Smith", "Jones" };
Console.WriteLine(names[3]);
```
**Error:** `IndexOutOfRangeException` (runtime crash)
**Fix:** ______________________
**Page ref:** 24-25 (3 items = indices 0, 1, 2. `[3]` doesn't exist)

---

**BUG 8:**
```csharp
if (age > 18)
{
    string status = "Adult";
}
Console.WriteLine(status);
```
**Error:** `The name 'status' does not exist in the current context`
**Fix:** ______________________
**Page ref:** 18-19 (scope — variable dies when `}` closes. Declare it before the `if`)

---

**Fill in the fixes. Write them out by hand or type them. This is your error-reading training. Every bug here is one you've already made or will make.**

---
---

## EXERCISE 11 — THE FULL PATTERN (FINAL CUMULATIVE)
**Workbook:** Part 1B Section 11 | **Pages 31-32**
**Concepts:** Everything. Declare, input, process, branch, loop, format, file I/O, error handle.
**Cumulative from:** EVERY exercise. This is the boss fight.

---

**The program:**
```
=== MISSION CALCULATOR ===
What's the op name? NIGHTFALL
How many personnel? 4
Hours estimated? 6
Hourly rate? 45.50

=== BRIEFING: NIGHTFALL ===
Team size: 4
Duration: 6 hours
Cost per person: $273.00
Total mission cost: $1,092.00

Affordable? (budget under $2000): Yes

=== PERSONNEL ===
1. Operator 1 — $273.00
2. Operator 2 — $273.00
3. Operator 3 — $273.00
4. Operator 4 — $273.00

Proceed? (yes/no) yes
NIGHTFALL is a go. Logged to file. Vidimus Omnia.
```

---

**LINE 1:**
```csharp
Console.WriteLine("=== MISSION CALCULATOR ===");
```

---

**LINE 2-3:**
```csharp
Console.WriteLine("What's the op name?");
string opName = Console.ReadLine();
```
- **WHAT:** Get the operation name.
- **WHY:** Ex1.
- **HOW:** Page 21-22.

---

**LINES 4-15 — Safe number inputs (Ex7 pattern x3):**
```csharp
int personnel = 0;
int hours = 0;
double rate = 0;
bool valid = false;

Console.WriteLine("How many personnel?");
valid = false;
while (!valid)
{
    try { personnel = int.Parse(Console.ReadLine()); valid = true; }
    catch (FormatException) { Console.WriteLine("A number:"); }
}

Console.WriteLine("Hours estimated?");
valid = false;
while (!valid)
{
    try { hours = int.Parse(Console.ReadLine()); valid = true; }
    catch (FormatException) { Console.WriteLine("A number:"); }
}

Console.WriteLine("Hourly rate?");
valid = false;
while (!valid)
{
    try { rate = double.Parse(Console.ReadLine()); valid = true; }
    catch (FormatException) { Console.WriteLine("A number:"); }
}
```
- **WHAT:** Three safe inputs — two ints and one double.
- **WHY:** Ex7 revision (try/catch + while). Notice `rate` uses `double.Parse()` instead of `int.Parse()` because hourly rate has decimals. Ex2 revision (double type).
- **HOW:** Reusing the `valid` flag by resetting it to `false` before each input loop. Page 27-29, 35.

---

**LINES 16-19 — Calculate:**
```csharp
double costPerPerson = rate * hours;
double totalCost = costPerPerson * personnel;
```
- **WHAT:** Arithmetic with variables.
- **WHY:** Ex3 revision — operators.
- **HOW:** `double * int` gives `double`. C# promotes automatically. Page 23.

---

**LINES 20-27 — Formatted output (Ex8 revision):**
```csharp
Console.WriteLine($"\n=== BRIEFING: {opName} ===");
Console.WriteLine($"{"Team size:",-20}{personnel}");
Console.WriteLine($"{"Duration:",-20}{hours} hours");
Console.WriteLine($"{"Cost per person:",-20}{costPerPerson:C}");
Console.WriteLine($"{"Total mission cost:",-20}{totalCost:C}");
```
- **WHAT:** Formatted output with left-aligned labels and currency.
- **WHY:** Ex8 revision — `{value,-20}` padding, `:C` currency.
- **HOW:** Page 29.

---

**LINES 28-36 — If/else (Ex9 revision):**
```csharp
double budget = 2000;
Console.Write($"\nAffordable? (budget under {budget:C}): ");
if (totalCost <= budget)
{
    Console.WriteLine("Yes");
}
else
{
    Console.WriteLine($"No — over budget by {totalCost - budget:C}. Cut something.");
}
```
- **WHAT:** Compares total cost against a budget.
- **WHY:** Ex9 revision — `if/else` with comparison operators. Arithmetic in the interpolation.
- **HOW:** Page 29-30.

---

**LINES 37-43 — For loop with formatting (Ex4 + Ex8):**
```csharp
Console.WriteLine($"\n=== PERSONNEL ===");
for (int i = 1; i <= personnel; i++)
{
    Console.WriteLine($"{i}. {"Operator " + i,-18}{costPerPerson:C}");
}
```
- **WHAT:** Prints each operator with their cost.
- **WHY:** Ex4 revision (for loop), Ex8 revision (formatting). Loop count is the user's input.
- **HOW:** `"Operator " + i` concatenates the string with the number. Page 25, 29.

---

**LINES 44-54 — Confirm and log (Ex5 while + Ex6 file + Ex9 if):**
```csharp
Console.WriteLine($"\nProceed? (yes/no)");
string confirm = Console.ReadLine();

if (confirm == "yes")
{
    string[] log = {
        $"Operation: {opName}",
        $"Personnel: {personnel}",
        $"Hours: {hours}",
        $"Rate: {rate:F2}",
        $"Total: {totalCost:C}"
    };
    File.WriteAllLines(@"C:\Users\gwu07\Desktop\PROG\missionlog.txt", log);
    Console.WriteLine($"{opName} is a go. Logged to file. Vidimus Omnia.");
}
else
{
    Console.WriteLine($"{opName} scrubbed. No log created.");
}
```
- **WHAT:** Asks for confirmation. If yes, writes mission details to a file. If no, aborts.
- **WHY:** Ex5 revision (ReadLine into string for comparison), Ex6 revision (File.WriteAllLines with @""), Ex9 revision (if/else with == comparison). Also uses `:F2` from Ex8 for the rate.
- **HOW:** Page 16 (==), 26-27 (file I/O), 29 (:F2 format), 29-30 (if/else).

---

**LINE 55:**
```csharp
Console.ReadLine();
```

---

**CUMULATIVE CHECK — EVERYTHING:**
| Concept | From | Page |
|---------|------|------|
| Console.WriteLine / ReadLine | Ex1 | 21 |
| $"" interpolation | Ex1 | 22-23 |
| string, int, double, bool | Ex2 | 22 |
| int.Parse, double.Parse | Ex3 | 35 |
| Arithmetic operators | Ex3 | 23-24 |
| Arrays (string[]) | Ex4 | 24 |
| for loop | Ex4 | 25 |
| while loop | Ex5 | 26 |
| File.WriteAllLines, @"" | Ex6 | 26-27 |
| try/catch, FormatException | Ex7 | 27-29 |
| :C currency, :F2 fixed, padding | Ex8 | 29 |
| if/else, ==, <=, && | Ex9 | 29-30 |
| Console.Write (no newline) | Ex9 | 34 |
| Scope awareness | Ex7 | 18-19 |

**TOTAL: ~55 lines. Every C# concept from Part 1B in one program. If you can write this from scratch, you own the material.**

---
---

# PART 2: HTML / CSS / JAVASCRIPT EXERCISES

*Coming next. Same format — line by line, WHAT/WHY/HOW, cumulative, page references to Part 2 of the workbook (Pages 46-94).*

---

# PART 3: SQL EXERCISES

*Coming after Part 2. Same format — line by line, WHAT/WHY/HOW, cumulative, page references to Part 3 of the workbook (Pages 94-122).*

---

# APPENDIX: EXERCISE TRACKER

| # | Exercise | Status | Skills |
|---|----------|--------|--------|
| 1 | First Program | ✅ DONE | Print, read, store, interpolate |
| 2 | Variables & Types | ✅ DONE | string, int, double, bool, const |
| 3 | Operators | ✅ DONE | Arithmetic, int.Parse, Math class, casting |
| 4 | Arrays | ✅ DONE | string[], int[], [index], .Length, parallel, for |
| 5 | Loops | ⬜ IN PROGRESS | foreach, while, != |
| 6 | File I/O | ⬜ | ReadAllLines, WriteAllLines, @"" |
| 7 | Try-Catch | ⬜ | try/catch, FormatException, scope |
| 8 | String Formatting | ⬜ | :C, :F2, padding, alignment |
| 9 | If/Else | ⬜ | if/else if/else, ==, !=, &&, \|\| |
| 10 | Error Decoding | ⬜ | Read broken code, find bugs |
| 11 | Full Pattern | ⬜ | EVERYTHING combined |

---

Vidimus Omnia.
