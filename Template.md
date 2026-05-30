# Template Description for AI Agents/Human Readers
## Basic Structure and Component Definition
- '# Title': The title itself literally. Marks what the document is for.
- '## (Condition)': A part(paragraph) of document where the project's status at a particular condition is stored in a form of Component tree
  - The condition can be anything that distinguishes among subprojects.
    - e.g. Timestamp, Edition, Version, Branch, Platform, etc.
  - Every Version(State) is expressed in present tense, like the Version/Build is existent right now.


- Keywords: The field that labels the information about each version's state and/or structure


  - Keyword lines are written like: '- [Keyword]: [content]'
    - Every line except title and version must be a keyword line.
    - Only keywords listed below are allowed.
    - The above equals to: "Every line, except '#(Title)' or '##(version)', MUST be formatted like: '(indentation)(a single dash)(space)(keyword)(colon)(space)(content)' "
    - This also means: "Titles(Headings beginning with #) are NOT allowed for keyword lines"


  - Every Keyword can be numbered like: '- \[keyword](\[number]): '
    - Keywords without numbers are considered '- \[keyword](0)', and have the highest priority among the lines with the same keyword.
    - Keyword lines with lower numbering have higher priority over others.
    - This feature is useful for grouping related keyword lines together.


  - Keyword lines can be preceded by one or more steps of indentation (1 step = 2 spaces)
  - Below are the list of keywords and their usage:


  - Component: The component itself literally.
    - Can point to any type or kind of element in the project.
    - Component can belong to another Component, which is indicated by indentation.


  - Text: The most basic entry. Plain literal text.
    - This type of keyword line is for writing some trivial notes that are certainly not important
    - Or providing a string literal within the document.
    - For important things that don't have any proper keyword, use '- Prio(n): (type): (content)' instead.


  - Description: The field where a Component's feature and details are explained.
    - Description keyword without number is considered 'Description(0)', and is the main Description of the Component.


  - Range: A line containing a list of Components under an Abstract Component(Not an actually existent Component; A Concept-Only Component for explaining, defining, or grouping one or more feature(s))
    - (OR) A line containing a list of Components under an Actually Existent Component
  - dRange: Range as a Description; Range expressed as one or more lines of Description instead of a list.
    - cannot be used with Range within a Component


  - Goal: A field that tells/explains which feature or state is required by a Component
  - Prio: A field where contains the most demanded work for now (now: the state expressed in a version)


  - Stage: A field that tells in which stage the Component is within a dev workflow
    - Available Stages: Issue, Implement, Testing, Dev, Edge, Production, Stable(Fallback)
    - Issue: An Issue Occured, or An Idea is Issued
      - Idea only
      - A Stage where Implementation effort has not begun nor is planned
    - Implement: A Stage where the first Implementation is made
      - Before the first working Implementation is out
    - Testing: A Stage where the Implementation is exposed to test cases, and then debugged
    - Dev: A Stage where the Implemetation is included/merged as a part of the current Project
      - Compatibility and/or Dependency, etc. can be tested for seamless integration
    - Edge: A Stage where the current Project has a Developer Build that contains the Implementation
    - Production: A Stage where the Edge branch is stabilized enough to be pulled to Production for End-Users/EndPoints
      - A Stage where the actual Update/Release is generated for End-Users
      - Therefore, Production is the actual stable branch in normal Project workflows.
    - Stable/Base: The Stable Previous Version(Good ol' days version); A Stage that provides rollback/fallback when the latest development Build fails.
      - prefer Base to avoid confusion with other workflow templates.


  - R: (Real/Resource) The prefix that comes before a name of an Actually Existent Component, no whitespace allowed after colon(:).
  - C: (Conceptual) The prefix that comes before a name of Concept-Only/Abstract Component, no whitespace allowed after colon(:)
    - The elements following any prefix can be grouped in parentheses. In this case, the prefix before group applies to every group element.
    - Elements containing whitespace also must be nested in parentheses.
    - Group Elements are separated by comma(,)
      - If the Element itself contains comma, use double comma(,,) for literal comma.
  - Other custom prefixes: can be declared/defined according to Project features

# Describe the Project here
