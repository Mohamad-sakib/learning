**_learnings In js_**

**literals** --> expression evaluates to a itself<br>

**variable** --> is can be think of memory block that hold a data or dataStructue;

**idenftifers** --> are name given to any thing in js

**expression** --> peice of code evauate to a value

**statments** --> are instruction that tell js to make some action but never evautates to a value unlike expression however some statements contain expression, produce a value that is turn out of action it make.<br>

**for while if else switchCase**

**string** --> sequecnce or collection of char in consecutive memoryLocations(indexed,immutable,rich in methods for string manipulation).<br>

**block** --> block of code that creates its own **scope**(tells what is accessable to where).<br>

**functions** --> is block of code that map some set of values with others(useCase: code reuseablity,abstraciion,maymore)<br>

**stringsMethods(String Class)** --> (methods are behavior of class's object)

**for of loop**

**recursion**

**array** --> is dataStrucutre that holds multiple data of diffrent data type in consecutive memory location.is used to stord multiple data in single variable.(indexed,mutable,rich in methods);

**arrayMethods(array Class)** -->push,pop,unshift,shift,splice,indexOf,lastIndexOf,slice,reverse,at,with,toSort,join,fill,concat,includes,keys,values.

**Map,Filter,Reduce,Every,Some,From,Find,Flat,Flatmap**

**Sort**

**ShallowCopy Vs DeepCopy**

**Class,Static ,Instance Property and Static , Instance Methods of Class**

**object {key:value}**

**array and object spreading**

**Object class and its methods(keys,values,entries)**

**data Organization**

**anominous function**

**function as variable const a = function () {}**

**arrow function ()=>{}**

**clouser and curring function {(x) => (y) => x+y}**

**Set**

**import,export**

**testCases and testFrameWork**

**assertLibrary(assertEqual())**

**Deno.test()**

**Deno extension**

**refactoring**

**string template**

**regular expression**

**had a cricket score board assigment** ==> impostance of templates
==>when to use array and object
==>searching in array is being super passed by finding key in object;
==>groupBy(no need of use it but it exist and powerfull tool)
==>fetch as many data can be fetched in one iteration means if you need to traverser same datastructure again and again for diffrent qeries then make done as many quesies you can do in once traverse. like deliveries were being fetched;
==>creating template for objects
==> NO prepating data in advance until requested
==> impostance of testing
==>testing using den.test() and assert liberary

**testing with description() and it() or test() function to create categories of tests**

**call() <==> apply() <==> bind**

**this{calling context}**

**json format to store and transfer data for js environment(java script object notation like xml in java)**

## standardData(that support source code, standard support program)

standardData <==VS==> userData(that modifies)

**json function{stringify(),parse()}**

**Deno.readTextFileSync() to read file, Deno.writeTextFileSync to wrtie file**
**object light testing** `JSON.stringfy(obj1) === JSON.stringfy(obj2)`
**ObjectDeepCopy ==> `JSON.parse(JSON.stringfy(obj1))`**
**permessions** ==> to give permison in once `-A`

```javascript
const display = console.log;

const readFile = () => {
  const filePath = Deno.args[0];
  const content = Deno.readTextFileSync(filePath);
  display(content);
};

readFile();
```

**errorhandeling** using `try ,catch ,finally block`

**snipit** --> code templates.

every process end returning its exit code that tell sucess status of process
all non zero are considered as symbol of not successfull and 0 only represents sucess;

mocking --> faking third party function to test function or functionality written in code that depends on.
`like`

```javascript
cosnt files = {
  "10_lines.txt" ="1\n2\n3\n4\n5\n6\n7\n8\n9\n10";
  "5_lines.txt" = "1\n2\n3\n4\n5";
  "11_lines.txt" = "1\n2\n3\n4\n5\n6\n7\n8\n9\n10\n11"
}

Deno.readTextFileSync = (path) => files[path];//overwriding Deno obj's readTextFileSync function for deno process evalualtes current progarm only by a fake function that return expected data that should be returned,if thirdpart methods's behavious as expected and it even notify that third part method is not working as expected if , test cases passes but when actual is used cause error; this all is to check a functionality created and depends on thirdpart works ok or not; if all test passes that means functionality created working properly while thirdpart not;

const readFile = (path) => Deno.readTextFileSync(path);

const head = (path) => readFile(head).split("\n").slice(0,10).join("\n");

"to check head we need to mock readfile to provide expected content of pathed file to head to check whether head is working properly or not"

```

**when we need to isolate functions in new file to spreate category of fn in single to file that ease in testing because you want only fns to execute that are imported while imported in test file not other fns then it.**

`like`

```javascript
const main() = head(Deno.arg[0]);
main();
//might return and print or require something (arg[0]) that is not available yet in development in program or can call function with Invalid data can cause error like calling head with undefined;
//like above if head is imported to get tested first this is file is executed by deno to provide reference of head but this import will throw error as while importing it deno first execute or get fn read to get imported while doing it even execute main() and here main i don't first want to execute, second it is passing Deno.arg[0] to head that is undefined as no files is passed since we are just imporitng the function than it call head with undefined lead to unwanted bheaviour, could be error or print something unwanted on screen
//therefore we need to sepreate both of them;
```

**learning** -`follow the process that lead to progress` -`keep asking question to yourself;` -`making assumptions mostly initally for io and unitlites` -`only mock the thirdPart methods for testing always` -`try to most thing automaited` -`toDOlist ,make,complete tasks,update it and  complete,update keep doing ` -`seprate thinking or thought process and mind flow anothewise it ends up with mesh`

flow --> (think of solution at idea state) --> think of modules --> write all modules --> take each module one after another --> think of its functinalities and requirement --> built them --> think for another -->write --> bulid --> next unitl all over.

once have tasks for module --> write first test cases for the task then implement accoring to requirement i.e follow the process towards progress;

**Deno.exit()** to set exit immedielty with exit code given to it ;
or Exit code can also be updated changing the varibale **Deno.ExitCode**

if ExitCode is 0 means process executed successfully and non zero value means process did execute successfully.

**AssertThrows** to test fns throw errors

**beforeEach(),afterEach(),beforAll(),afterAll() for testing.**
**creating error templates** so that errorMsg can be formated as per user requirement
throwing errors using **throw** and catching it using ""**catch block**""
**tryCatchBlocks**

```testing guidelines
- Testing

  - Separate test file per src file
  - describe/it naming conventions

    - Name behaviour over values
      - Correct:
        it('should extract as many lines as the file size when file is smaller than count option')
      - Incorrect:
        it('should give 5 lines for head(-n,ten_lines.txt))

  - assertThrows
    - use assertThrows to test errors that are being thrown from Deno.readTextFileSync
  - mock in beforeEach

- No strings. Only strings at entry/exit
- Consider enriching data in stages
- Validation can happen in more than one place
- Decide wisely between objects and arrays.
  - Do you have an order?
  - Do you have names?
- No need to throw errors. Errors can be handled by returning values as well.
- Test units. Each separate stage can be tested on its own by assuming that the other stages work well.
- Use console.error to print to error stream
- Use Deno.exit while exiting
- Throwing errors
  - throw richer objects
```

**synchronous and Asynchronous execution** and **synchronous and Asynchronous execution fns**

**Deno.readTextFileSync();** to read file sunchrounously
**Deno.readTextFile();**to read file Asynchronously
**setTimeout() and setInterval() both are asynchnrous fns**
**console.error**

# flow of execution cann't always be same like describe and it doestn't work as seems

# catch all error of progarm at same place.

what is Opps ?
why to learn Opps?

Opps(object oriented programming)

1. class and instance of class.
2. creation of class and its object
3. initializing instance of class
4. constructer
5. public and private fields
6. public and private methods
7. rules for class creation and what can be written in it.
8. new keyword to create instance of class
9. . opertor (member operator)
