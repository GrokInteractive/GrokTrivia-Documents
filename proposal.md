<img src="http://www.grok-interactive.com/images/grok-logo.svg" alt="Grok Logo" style="margin-left: -165px; left: 50%; position: relative;">

# Grok Trivia

## Purpose

Grok's current model relies upon a confederation of independent projects and developers.  

The purpose of this task is to evaluate Grok's ability to work on singular objective as individuals and teams, in order to develop products in addition to--or in lieu of--providing services.

## Objective

The objective for Grok Trivia is to create a trivia game with three independent components: a server, a web-based client, and an iOS client.

### High-Level MVP

The server will:

- Provide a list of categories
- Provide a list of questions in a given category
- Accept client answer and return a correct/incorrect response

The clients will:

- Provide a UI to select a question category
- Provide a UI to answer questions

### Entities

- Category
  * Name
  * Has Many Questions
- Question
  * Question
  * Correct answer
  * Fake Answers


## Assignments

- Phoenix
  * Christopher Moeller
  * Oliver Garcia

- Ember
  * Jeffrey Jurgajitis
  * Anton Domratchev

- iOS
  * Josh Freeman
  * Joseph Villafranca
