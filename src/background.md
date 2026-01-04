# Background

The idea for this application came to me while reflecting on the countless journeys I had taken. Despite all the places I had visited, I found myself forgetting key moments and locations. Friends would ask about my travels, and I often struggled to recall the details or find the photos that matched those memories. I realized I needed a way to not only document my trips but also retrieve the content of the documentation with ease.

That is how **Immer in Bewegung** was born. The name, meaning *always in movement* in German, perfectly encapsulates the heart of this project. To bring this concept to life, the frog is chosen as the mascot—a symbol of endless motion and adventure.

> [!NOTE]
> You can check out the online app running at [https://online.bewegung.app/](https://online.bewegung.app/). If you want to bind your own data, you can do so via [https://online.bewegung.app/?path=source](https://online.bewegung.app/?path=source).

## Basic idea

Over time, most code in applications becomes obsolete. To ensure your memories are not lost to such obsolescence, the core idea of this project is to visualize travel data stored in SQLite format. SQLite databases are easy to update using any of the many available tools, offer long-term reliability, and are more likely to remain compatible with future technologies. This makes it a solid, future-proof solution. However, scrolling through a database directly can be tedious—so why not build an interface on top? But this project is not just an application; it's a versatile syntax that allows you to take travel notes in a simple and structured way.

### Three main features

- A single SQLite database compliant with the Immer in Bewegung Trip Syntax
- Use directly on GitHub or host it on your own server
- Use in conjunction with Immich to combine your documentation with photos (optional)

![img](img/swe.svg) **Made in Sweden**
