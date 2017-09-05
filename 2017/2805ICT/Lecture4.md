## Main Concepts
- Relationships between requirements and designs: transformation of models, design by contracts, invariants
- Using components: component selection, design, adaptation and assembly of components(e.g. building a GUI using a standard widget set)
- Case Studies

### Transformation of Models
Four types of transformations:
- Model transformation
E.g.
3x diff user classes with string email;
--->
1x User parent class with 3x children
- Forward engineering
- Reverse engineering
- Refactoring: the process of changing a program in such a way that it does not alter the external behaviour of the code, improving its internal struct
__Pull Up Field:__ 
```
public class User{
    private String email;
}

public class Player extends User{
    //...
}
```
__Pull Up Constructor Body__
```
public class User{
    public User(String email){
        this.email = email;
    }
}
public class Player extends User{
    public Player(String email){
        super(email);
    }
}
```
### Design by Contract
- Language that implements Design by Contract principles: Eiffel
__What?__
- Two parties: Client which requests a service & Supplier which supplies the service
- An Agreement between client and supplier
__Relation to Software Design__
- Pre and post conditions of a procedure as obligations and benefits of a contract between the client (the caller) and the supplier (the called procedure)
- Promotes using pre and post-conditions (written as assertions) as a part of module design

In Eiffel:
```
put_child(new_child: NODE) is
-- Add new to the children of current node
require
    new_child /= void
do
    ...Insertion algorithm...
ensure
    new_child.parent = Current;
    child_count = old child_count + 1
end -- put_child
```
### Invariants
- Class invariants are checked @ the entry and exit of every public methond in the class.
- THe invariant is defined in a method called "_Invariant" that takes no arguments and returns a boolean
```
protected boolean _Invariant() {
    return size() >= 0;
}
```






