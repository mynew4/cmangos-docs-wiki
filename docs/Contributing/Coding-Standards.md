It is highly recommended to use a single **coding style** for the whole project source code. Exceptions are allowed for independent libraries used in the project, but it is generally advisable all contributors to use this style.

### Tab size

First of all, we use space. Tabs are four-character width. That is, no 8-space tabs, no 2-space tabs. Four. Unfortunately there's no such thing as 'standard tab width', and 4-space indenting looks best from our point of view, besides MSVC' editor has this setting by default.

### Line length

Then, please use 80-character wide lines. If your line is way longer than that, please split it. If it's just a little longer, so be it. The continuation text, if you're splitting text inside the brackets, should be indented to the position after the opening bracket:

      printf("This is a example of how we split lines longer than %d characters\n"
              "into several so that they won't exceed this limit.\n",
              max_sourcecode_width);

If you have long strings, you can split them as shown above, just remember that C/C** compilers will glue together several strings that come without any special characters between them into one.

### Brackets

Now we use symmetric bracket placement, closing bracked under the opening bracket:

    if (something)
    {
        ...;
    }
    else
    {
        ...;
    }

    switch (x)
    {
        case 1:
            printf("X is one!\n");
            break;
        case 2:
        {
            printf("X is two!\n");
            break;
        }
    }

    for (int i = 1; i < 3; ++i)
    {
        printf("I is %i!\n", i);
    }

Every bracketed block moves its contents by one tab to right. Labels (but not case selectors or 'public:/private:/protected' C** keywords) are placed at the leftmost indention position for the current block, that is, in the same position where enclosing brackets are. Also please don't use brackets around a single statement because it clutters the code with unneeded stuff; use brackets only when using non-obvious constructs, like:

    if (...)
    {
        if (...)
            ...;
    }
    else
        ...;

Also, please place one space before opening parenthesis. Before, but not after (the if ( blah ) style is a no-no!).

### Class declaration and constructors

    class Class : public Parent
    {
        public:
            Class() : Parent(0),
                m_field(1)
            {
                func();
            }

           void func() {}

        private:
            int m_field;
    };

Main points:
a) space before and after : in class parents list and constructor body
b) next line and indent for class field initialization list
c) indent for public:/private:/protected: section with additional indent for section content
d) empty or short function body can be at same line with declaration in in-class definition case

### Code documentation with Doxygen

Now, please use DoxyGen-type comments. This is a bit similar to JavaDoc comments and to other automatic code documentation generation tools. One-line documentation should be placed in `///` (three slashes) comments, multi-line comments should be put in a `/** ... */` block (slash-two-stars).

Here's a example that shows most useful keywords that you can use in a comment block:

      /**
       * This function does something very useful. If used with care, this function
       * has the potential to make your programs really really useful.
       *
       * \arg \c x
       *   The x argument specifies a integer that is transformed into something useful.
       * \arg \c y
       *   This argument, if not NULL, is a pointer to a free memory area where this
       *   function will put something really really useful.
       * \return
       *   A useful value, or NULL if error.
       *
       * Here is a example that you can paste into your code so that it saves you a
       * lot of typing:
       *
       * \verbatim
       * for (int x = 0; x < 100; ++x)
       *     printf("DoSomethingUseful%d = %s\n", i,
       *             DoSomethingUseful(i, &ScratchPad));
       * \endverbatim
       *
       * Paragraphs are split from each other by inserting a empty line. Also some HTML
       * tags are supported, like <ol> [<li>...] </ol> and <ul> [<li>...] </ul> for
       * ordered (numbered) and unordered (dotted) lists respectively.
       */
      char *DoSomethingUseful(int x, void *y);

      /// This is a one-line comment
      void Something();

Use normal comments (`//` and `/* ... */`) only if you want to make a comment that shouldn't go into the automatically annotated code (like `/* shit ... this does not work */`).
