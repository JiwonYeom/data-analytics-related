# Practice Pattern 1

```python
class Button(object):
    html = ""
    def get_html(self):
        return self.html

class Image(Button):
    html = "<img></img>"

class Input(Button):
    html = "<input></input>"

class Flash(Button):
    html = "<obj></obj>"

class ButtonFactory():
    def create_button(self, typ):
        targetclass = typ.capitalize()
        return globals()[targetclass]()

button_obj = ButtonFactory()
button = ['image', 'input', 'flash']

for b in button:
    print(button_obj.create_button(b).get_html())
```

# Practice Pattern 2
```python
class Car(object):
    @staticmethod
    def factory(type):
        if type == "Racecar":
            return Racecar()
        if type == "Van":
            return Van()
        assert 0, "Bad car creation: " + type

class Racecar(Car):
    def drive(self): print("Racecar driving.")

class Van(Car):
    def drive(self): print("Van driving.")

obj = Car.factory("Racecar")
obj.drive()
```