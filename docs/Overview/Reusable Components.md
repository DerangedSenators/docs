# Reusable Components

There is a core principle in software development known as DRY. DRY stands for Don't Repeat Yourself. This document will detail the steps you can take to ensure that all components in our project are written with this principle in mind.

## Reasoning
Our project specification says that we are a startup company preparing to release our product into the market. Typically companies plan ahead and don't stick with a single product on their portfolios. This is something we should keep in mind when creating our product.
Therefore, When you begin to create a component be it scripts or assets, you must think about the reusability of that compnent. Can it be implemented into a future product. If this is the case, you must think about developing it as a reusable component.

=== "Unity"
    Unity offers a unique solution to the creation of reusable components through the use of [Custom Packages](https://docs.unity3d.com/Manual/CustomPackages.html). These packages can hold scripts, native objects, assets and more. It is widely recommended that you create a custom package when creating a Unity Reusable Component.
    ### Steps towards making a custom package
    1. Speak to another team member about converting an existing component or creating a new component as a package
    2. Create another repository on our github organisation to hold the package*
    3. Follow the steps found in the unity documentation to develop your component
    4. Once ready to include in the product, Include it as a [Git Dependency](https://docs.unity3d.com/Manual/upm-git.html) in the product's packages.json file. This will allow the editor to fetch the latest version directly from git, simplifying the import process
=== "C/C++"
    Reusable C/C++ code must be compiled into a seperate shared or static library (depending on how it needs to be used) and then imported into the project.

