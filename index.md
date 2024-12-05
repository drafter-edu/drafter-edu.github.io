---
title: Drafter
feature_text: |
  ## Drafter
  Drafter is an educational web development library for Python
excerpt: "Drafter is an educational web development library for Python. It enables students to learn and practice programming concepts by building dynamic, interactive websites."
---

Drafter is an educational web development library for Python. It enables students to learn and practice programming concepts by building dynamic, interactive websites.

* [Drafter Quick Start Guide](https://drafter-edu.github.io/drafter/quickstart/quickstart.html)
* [Drafter Student Documentation](https://drafter-edu.github.io/drafter/students/docs.html)
* [Drafter Workbooks]()
* [More Examples](https://drafter-edu.github.io/drafter/examples/examples.html)
* [Deploying Drafter on GitHub Pages](https://drafter-edu.github.io/drafter/students/deployment.html)

# Features

* Web Development Simplified: Build "full-stack" websites with minimal setup.
* State Management: Use Python dataclasses, lists, dictionaries, or any primitive types as the data model.
* Interactive Components: Add buttons, text boxes, images, and [more](https://drafter-edu.github.io/drafter/reference/components.html).
* Fully Testable: Drafter uses a model around simple functions and doesn't rely on global state, making it easy to [test](https://drafter-edu.github.io/drafter/students/testing.html) your sites.
* Instant Regression Tests: Drafter automatically generates tests cases based on your interactions with the site. No AI needed!
* Dynamic Content: Create multi-page applications with rich user interaction.
* Easy Deployment: Use [GitHub Pages](https://drafter-edu.github.io/drafter/students/deployment.html) to deploy your sites; no backend server required!

# Examples and Getting Started

You can install Drafter using your favorite editor's GUI, or via pip on the command line:

```python
pip install drafter
```

The simplest Drafter site is quite short:

```python
from drafter import *

start_server()
```

But it's not hard to make something more sophisticated!

```python
from drafter import *
from dataclasses import dataclass

@dataclass
class State:
    counter: int

@route
def index(state: State) -> Page:
    return Page(state, [
        "Welcome to Drafter!",
        "Click the button below.",
        Button("Increase the count", increment_counter)
    ])

@route
def increment_counter(state: State) -> Page:
    state.counter += 1
    return Page(state, [
      "You've clicked the button " + str(state.counter) + " times",
      Button("Click again", increment_counter)
    ])

start_server(State(0))
```

{% include counter-example.html %}

# Explore Tutorials

* [Cookie Clicker](https://drafter-edu.github.io/drafter/workbook/index.html#cookie-clicker): Click cookies to earn more cookies. Learn state management!
* [Bank Account](https://drafter-edu.github.io/drafter/workbook/index.html#bank-account): Manage deposits and withdrawals in a simulated bank system.
* [Simple Adventure Game](https://drafter-edu.github.io/drafter/workbook/index.html#simple-adventure-game): Explore a world of decisions and find the treasure.
* [Store](https://drafter-edu.github.io/drafter/workbook/index.html#store): Create a shop where users can purchase items.
* More examples can be found [here](https://drafter-edu.github.io/drafter/examples/examples.html)!

# Documentation

Ready to learn more? [Check out the student-friendly Drafter Documentation!](https://drafter-edu.github.io/drafter/quickstart/quickstart.html)

# About Drafter's Team

Drafter was created to simplify web development for students learning Python. The team includes passionate educators and developers dedicated to advancing programming education.

Follow us!

* [GitHub Repository](https://github.com/drafter-edu/drafter)
* [Discussion Board](https://github.com/drafter-edu/drafter/discussions)
* [Issue Tracker](https://github.com/drafter-edu/drafter/issues)
