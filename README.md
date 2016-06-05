# Introduction

This style guide means to address the proper spacing in a Swift file to achieve maximum readability. It may change over time and pull requests are greatly apreciated.

# Quick Comparison

[[TWO IMAGES OF THE SAME FILE WITH DIFFERENT APPROACHES]]

# Table of Contents

* [Headers](#Headers)
* [Footers](#Footers)
* [Imports](#Imports)
* [Blocks of Code](#Blocks-of-Code)
* [Comments](#Comments)
* [Other Separations](#Other-Separations)
* [Changes](#Changes)
* [Common Examples](#Common-Examples)

## Headers

Files should contain no headers. Any license text should be added on your project's `LICENSE.md` file or `README.txt` or similar, but not in each individual file. Autogenerated headers should not be included.

Avoid starting your files with things like:
```
//
//  Created by John Smith on 6/5/16.
//  Copyright (c) 2016 Smithy, Inc. All rights reserved.
//
```

The very first line of a file should be an `import`.

```
import Foundation
```

## Footers

Files should end with an empty line.

```
protocol MediaType {

  [code]
}

```

## Imports

Each `import` should occupy a new line. After all imports are declared, a blank line should be added before the entity declaration.

```
import Foundation
import MapKit

class SmithyMapViewController {

  [code]
```

## Blocks of Code

All blocks of code, in general should be treated the same. A block of code is delimited by `{` and `}`. A few rules apply to this.

#### 1. Opening
Blocks always open in the same line as the code that's declaring this block. Afterwards, a blank line should always be added.

```
class MyView: UIView {

  [code]
}
```

or

```
while total >= maximum {

  [code]
}
```

or

```
myView.keepAnimatedWithDuration(interval) {

  [code]
}
```

#### 2. Closing
Blocks close right after the last line of code of the block and leave a blank line to the next line of code, except it's a nested block and whose parent block needs to close as well.

Single close:
```
  [code]
}

[code]
```

Nested close:
```
    [code]
  }
}

[code]
```

#### 3. Intermediate
There are some flow control expressions that serve as connector for two blocks of code. In this case, both the opening and closing share the same line. A blank line of code should be added previous to this expressions, and like with every other opeining, an extra line should be added afterwards.

Some examples:
```
  [code]
  
} else if x > width {

  [code]
```

```
  [code]
  
} else {

  [code]
```

```
  [code]
  
} catch MyError.InvalidSelection {

  [code]
```

#### 4. Chaninng

Closures chaining is a special case of blocks of code. When chaining, consecutive closures invokations should start on a new line along with the `.` accessor.

```
array.map {

  [code]
}
.filter {

  [code]
}
.reduce("") {

  [code]
}

[code]
```

#### 5. Special case: The Switch Statement

The switch statement is special because it doesn't use curly braces to define the blocks of code that should be executed in each case. Indent `case`s in the same level as `switch` and use a blank line after every option and an extra blank line after it, unless it's the final option.

Like this:
```
switch compassPoint {

case .North:

  [code]
  
case .South:

  [code]
  
default:

  [code]
}

[code]
```

## Comments

For inline comments, a blank space should be added after the end of the code. For full line comments a blank line should be added before it. Both should have a space between the `//` and the comment itself.

In line:
```
print(name) // Prints the name of the user in the console.
```

Full line:
```
[code]

// We are safe to mark this as done since it's asigned to the current user.
if task.assignee == currentUser {

  [code]
}
```

## Other Separations

Blank lines can be used to separate different sections of code to create logical groups. A single line of separation should be enough.

SDK vs. 3rd parties imports:
```
import Foundation
import UIKit
import MapKit
import CoreLocation

import ReactiveCocoa
import EasyPeasy
```

Private vs. Public properties:
```
let name: String
let age: Int

private let apiClient: MyApiClient
private let credentialsStorage: MyCredentialsStorage
```

Initialization and configuration of different objects:
```
let firstNameLabel = UILabel()
firstNameLabel.text = "First Name"

let lastNameLabel = UILabel()
lastNameLabel.text = "Last Name"
```

## Changes
Adding tabs or extra spaces when commiting.

## Common Examples
