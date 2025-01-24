# Scala Default Constructor Bug

This repository demonstrates a subtle bug that can occur in Scala when using default constructors. The bug arises from the way the `this()` method is employed within a default constructor.

## Bug Description

In Scala, if you define a primary constructor with parameters, and you also want to provide a default constructor, you might do it by calling the primary constructor from the default constructor. But, if this call is not carefully managed or structured, it could result in infinite recursion or unexpected behavior. This is because the `this()` method, when used within a constructor, essentially delegates the construction process to a different constructor within the same class.

The primary constructor in the example has a parameter `x` of type `Int`. If you try to call the default constructor, the `this()` method call is expected to handle the instantiation of an object with a default value, which is in this case 0. However, if not implemented properly, this might lead to problems.

## Solution

To fix this issue, explicitly call the primary constructor using the desired default value: