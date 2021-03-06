NameParser
====

[![Join the chat at https://gitter.im/binaryfog/NameParser](https://badges.gitter.im/binaryfog/NameParser.svg)](https://gitter.im/binaryfog/NameParser?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


Parses names using English conventions for persons names. 
Intended to be extendable, the library can be extended just by implement `IFullNamePattern` interface and assign a score to the returned result.

For the sake of performance, the assembly and types implementing `IFullNamePattern` must be loaded before the first attempt to use the `NameParser`.

If you have a person name that is not parsed correctly, please post a message on https://gitter.im/binaryfog/NameParser. I'll see what I can do.

Usage:
```csharp
string fullName = "Mr. Jack Johnson"; 
FullNameParser target = new FullNameParser(fullName); 
target.Parse();
string firstName = target.FirstName;
string middleName = target.MiddleName;
string lastName = target.LastName;
string title = target.Title;
string nickName = target.NickName;
string suffix = target.Suffix;
string displayName = target.DisplayName;
```

Alternative usage:
```csharp
string fullName = "Mr. Jack Johnson"; 
FullNameParser target = FullNameParser.Parse(fullName);
string firstName = target.FirstName;
string middleName = target.MiddleName;
string lastName = target.LastName;
string title = target.Title;
string nickName = target.NickName;
string suffix = target.Suffix;
string displayName = target.DisplayName;
```
Jun. 17, 2017: Started a new related project Nameparser.Dataset on github as a repository for names and parsed names. Feel free to add there names and parsed names.

Nov. 13 2015: More cases are now handled. These are the cases:
* SR. John Henry William dela Vega, Jr Esq.
* MANUEL ESQUIPULAS SOHOM
* Maria Delores Esquivel-Moreno
* PHILIP DEHART ESQ
* DEHART, PHILIP
* john 'jack' kennedy
* john(jack) f kennedy
* kennedy, john(jack) f
* Mr.Jack Johnson, ESQ"
* Jose Miguel De La Vega
    
Jan. 8 2016: 100% code coverage. More test cases. These are the cases:
* Empty string and white space cases.
* Mr. Jack Francis Van Der Waal Sr.
* Mr. Jack Francis Marion Van Der Waal Sr.
