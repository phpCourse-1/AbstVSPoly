# Abstraction and Polymorphism

These two are among the most important characteristics of Object Oriented paradigm:

## Abstraction

Data Abstraction is the most important features of any OOPS programming language. It shows only useful information, remaining are hidden form the end user. Abstraction is the any representation of data in which the implementation details are hidden (abstracted).

```php
abstract class Animal {
    public $name;
    public $color;

    public function __construct($name, $color){
        $this->name = $name;
        $this->color = $color;
    }

    public function describe() {
        return $this->name . ' color is ' . $this->color;
    }

    // Abstract Method
    abstract public function makeSound();
}

class Dog extends Animal {
    public $sound;

     public function __construct($name, $color, $sound){
        parent::__construct($name, $color);
        $this->sound = $sound;
    }

    // Implement the Abstract Method
    public function makeSound() {
        return "The Sound $this->sound By the $this->name";
    }
}

$animal = new Animal();
$animal->name = 'Animal';
$animal->color = 'Brown';
echo $animal->describe(); // Animal color is Brown

$dog = new Dog('Dog', 'Black', 'Bark');
echo $dog->describe(); // Dog color is Black
echo $dog->makeSound(); // The Sound Bark By Dog
```

## Polymorphism
