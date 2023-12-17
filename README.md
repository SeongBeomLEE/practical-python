# 또 읽으면 좋은 내용
- [07_Objects](Notes/02_Working_with_data/07_Objects.md)
  - python에서 assignment operations 들은 절대 복사본을 만들지 않는다.
  - python에서 assignment operations 들은 단지 reference copy를 할 뿐이다. (pointer copy)
  - 따라서 리스트 안에 리스트를 넣고, 리스트 안에 있는 리스트의 값의 변화를 주면, 리스트안에 있는 리스트가 저장되어 있는 메모리의 값 자체가 변화한 것이기 때문에 해당 메모리를 잡고 있는 모든 값들이 변화하는 것이다. (이 내용을 유추해보면 리스트는 내부에 메모리 위치를 저장한다고 볼 수 있음)
  - 그런데 Variables은 memory locations을 의미하는 것이 이니라 name을 의미한다.
  - 따라서 a 라는 Variables에 새로운 값을 넣더라도, 기존에 a가 가지고 있던 값에 메모리에 변화를 주는게 아니라, 그냥 a라는 Variables이 다른 메모리 공간에 있는 값을 읽게 되는 것임.
  - python에서 (int, float, string)의 datatype은 read-only기 때문에 동일한 값을 가지면 동일한 메모리 위치를 공유함
  - list는 자체가 하나의 개체이기 때문에 리스트 내에 값이 모두 동일한 메모리 위치를 가지더라도 리스트 자체는 서로 다른 메모리 위치를 사용함
  - 따라서 동일한 메모리 위치를 공유하는 list(or set)를 deepcopy를 통해서 서로 다른 메모리 위치를 사용하게 만들 수 있음 (그런데 내부에 (int, float, string)의 datatype 값들은 동일한 메모리 위치를 공유함, 또한 set도 hashable type 만을 값으로 사용할 수 있기 때문에 내부 값들이 서로 같은 위치를 공유함, [What does "hashable" mean in Python?](https://stackoverflow.com/questions/14535730/what-does-hashable-mean-in-python))
  - python의 "is" 는 두 값이 서로 같은 메모리를 공유하는지 확인하는 것, 단순히 값이 같은지 여부를 판단하려면 "==" 를 사용하는 것이 좋음
  - python에서 Numbers, strings, lists, functions, exceptions, classes, instances, 등등 모든 것이 objects임
  - 이는 이름을 부여할 수 있고, 데이터로 사용할 수 있고, container에 담을 수 있고, 이 밖에 제약 없이 다양하게 사용할 수 있다는 것을 의미함
  - 이래서 때때로 모든 objects를 "first-class" 라고 부르는 것임 ([First Class functions in Python](https://www.geeksforgeeks.org/first-class-functions-python/))
- [06_Design_discussion](Notes/03_Program_organization/06_Design_discussion.md)
  - Function Design의 주요 목표는 모듈화와 예측 가능성임
  - python은 다른 프로그래밍 언어와 다르게, main function과 main method라는 개념이 없음
  - 그 대신 파이썬은 source file 들 중에 제일 처음 시작하는 파일의 __main__ check을 통해서 main module 처럼 사용할 수 있음
  - 함수의 예측 가능성을 높이기 위해서 Doc String, Type Annotation, arguments name 을 짧고 간결하게 작성해주는 것이 좋음
  - 상황에 따라 다르겠지만, 함수의 유연성은 때때로 더 나은 서비스를 만드는데 도움을 줄 수 있기 때문에, 예측 가능성을 위해서 함수의 유연성을 제한하는 것은 좋은 습관이 아닐 수 있음 (read_data 함수를 작성할 때, file_name을 받을 것이냐, Iterable 객체를 받을 것이냐, Duck typing)

# 공부 기록
- 2023.11.24 [02_Working_with_data/02_Containers](Notes/02_Working_with_data/02_Containers.md)
- 2023.11.25 [03_Program_organization/00_Overview](Notes/03_Program_organization/00_Overview.md)
- 2023.11.26 [03_Program_organization/05_Main_module](Notes/03_Program_organization/05_Main_module.md)
- 2023.12.17 [03_Program_organization/06_Design_discussion](Notes/03_Program_organization/06_Design_discussion.md)

# Welcome!

When I first learned Python nearly 27 years ago, I was immediately
struck by how I could productively apply it to all sorts of messy work
projects. Fast-forward a decade and I found myself teaching others the
same fun.  The result of that teaching is this course--A no-nonsense
treatment of Python that has been actively taught to more than 400
in-person groups since 2007.  Traders, systems admins, astronomers,
tinkerers, and even a few hundred rocket scientists who used Python to
help land a rover on Mars--they've all taken this course. Now, I'm
pleased to make it available under a Creative Commons license--completely
free of spam, signups, and other nonsense. Enjoy!

[GitHub Pages](https://dabeaz-course.github.io/practical-python) | [GitHub Repo](https://github.com/dabeaz-course/practical-python).

--David Beazley ([https://dabeaz.com](https://dabeaz.com)), [@dabeaz](https://mastodon.social/@dabeaz)

(P.S. This course is about Python. If you want a Python course that's about programming,
you might consider [Advanced Programming with Python](https://www.dabeaz.com/advprog.html))

## What is This?

The material you see here is the heart of an instructor-led Python
training course used for corporate training and professional
development. It was in continual development from 2007 to 2019 and
battle tested in real-world classrooms.  Usually, it's taught
in-person over the span of three or four days--requiring approximately
25-35 hours of intense work. This includes the completion of
approximately 130 hands-on coding exercises.

## Target Audience

Students of this course are usually professional scientists,
engineers, and programmers who already have experience in at least one
other programming language. No prior knowledge of Python is required,
but knowledge of common programming topics is assumed.  Most
participants find the course challenging--even if they've already been
doing a bit of Python programming.

## Course Objectives

The goal of this course is to cover foundational aspects of Python
programming with an emphasis on script writing, basic data manipulation, and
program organization.  By the end of this course, students should be
able to start writing useful Python programs on their own or be able
to understand and modify Python code written by their
coworkers.

## Requirements

To complete this course, you need nothing more than a basic
installation of Python 3.6 or newer and time to work on it.

## What This Course is Not

This is not a course for absolute beginners on how to program a
computer.  It is assumed that you already have programming experience
in some other programming language or Python itself.

This is not a course on web development.  That's a different
circus. However, if you stick around for this circus, you'll still see
some interesting acts--just nothing involving animals.

This is not a course on using tools that happen to be written
in Python. It's about learning the core Python language.

This is not a course for software engineers on how to write or
maintain a one-million line Python application. I don't write programs
like that, nor do most companies who use Python, and neither should
you. Delete something already!

## Take me to the Course Already!

Ok, ok. Point your browser [HERE](Notes/Contents.md)!

## Community Discussion

Want to discuss the course?  You can join the conversation on
[Gitter](https://gitter.im/dabeaz-course/practical-python).  I can't
promise an individual response, but perhaps others can jump in to help.

## Acknowledgements

Llorenç Muntaner was instrumental in converting the course content from
Apple Keynote to the online structure that you see here.

Various instructors have presented this course at one time or another
over the last 12 years. This includes (in alphabetical order): Ned
Batchelder, Juan Pablo Claude, Mark Fenner, Michael Foord, Matt
Harrison, Raymond Hettinger, Daniel Klein, Travis Oliphant, James
Powell, Michael Selik, Hugo Shi, Ian Stokes-Rees, Yarko Tymciurak,
Bryan Van de ven, Peter Wang, and Mark Wiebe.

I'd also like to thank the thousands of students who have taken this
course and contributed to its success with their feedback and
discussion.

## Questions and Answers

### Q: Are there course videos I can watch?

No. This course is about you writing Python code, not watching someone else.

### Q: How is this course licensed?

Practical Python Programming is licensed under a Creative Commons Attribution ShareAlike 4.0 International License.

### Q: May I use this material to teach my own Python course?

Yes, as long as appropriate attribution is given.

### Q: May I make derivative works?

Yes, as long as such works carry the same license terms and provide attribution.

### Q: Can I translate this to another language?

Yes, that would be awesome.  Send me a link when you're done.

### Q: Can I live-stream the course or make a video?

Yes, go for it!  You'll probably learn a lot of Python doing that.

### Q: Why wasn't topic X covered?

There is only so much material that you can cover in 3-4 days.  If
it wasn't covered, it was probably because it was once covered and it
caused everyone's head to explode or there was never enough time to
cover it in the first place.   Also, this is a course, not a Python
reference manual.

### Q: Why isn't awesome `{command}` in awesome `{tool}` covered?

The focus of this course is on learning the core Python language,
not learning the names of commands in tools.

### Q: Is this course being maintained or updated?

This course represents a "finished product" that was taught and
developed for more than decade.  I have no plans to significantly
revise the material at this time, but will occasionally fix bugs and
add clarification.

### Q: Do you accept pull requests?

Bug reports are appreciated and may be filed through the
[issue tracker](https://github.com/dabeaz-course/practical-python/issues).
Pull requests are not accepted except by invitation. Please file an issue first.

