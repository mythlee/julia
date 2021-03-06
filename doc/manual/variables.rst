
***********
 Variables
***********

Julia provides an extremely flexible system for naming variables.
Variable names are case-sensitive, and have no semantic meaning (that is,
the language will not treat variables differently based on their names).

.. raw:: latex

    \begin{CJK*}{UTF8}{gbsn}

.. code-block:: guess

    julia> ix = 1.0
    1.0

    julia> y = -3
    -3

    julia> Z = "My string"
    "My string"

    julia> customary_phrase = "Hello world!"
    "Hello world!"

    julia> UniversalDeclarationOfHumanRightsStart = "人人生而自由，在尊严和权力上一律平等。"
    "人人生而自由，在尊严和权力上一律平等。"

.. raw:: latex

    \end{CJK*}

Unicode names (in UTF-8 encoding) are allowed:

.. raw:: latex

    \begin{CJK*}{UTF8}{mj}

.. code-block:: guess

    julia> δ = 0.00001
    0.00001

    julia> 안녕하세요 = "Hello" 
    "Hello"

.. raw:: latex

    \end{CJK*}

Julia will even let you redefine built-in constants and functions if needed::

    julia> pi
    π = 3.1415926535897...
    
    julia> pi = 3
    Warning: imported binding for pi overwritten in module Main
    3
    
    julia> pi
    3
    
    julia> sqrt = 4
    4
    
However, this is obviously not recommended to avoid potential confusion.

Allowed Variable Names
======================

Variable names must begin with a letter (A-Z or a-z), underscore, or Unicode
character with code point greater than 00A0. Subsequent characters may also include
! and digits (0-9).

All operators are also valid identifiers, but are parsed specially. In some
contexts operators can be used just like variables; for example ``(+)`` refers
to the addition function, and ``(+) = f`` will reassign it.

The only explicitly disallowed names for variables are the names of built-in
statements::

    julia> else = false
    ERROR: syntax: unexpected else
    
    julia> try = "No"
    ERROR: syntax: unexpected =


Stylistic Conventions
=====================

While Julia imposes few restrictions on valid names, it has become useful to
adopt the following conventions:

- Names of variables are in lower case.
- Word separation can be indicated by underscores (``'\_'``), but use of
  underscores is discouraged unless the name would be hard to read otherwise.
- Names of ``Type``\ s begin with a capital letter and word separation is
  shown with CamelCase instead of underscores.
- Names of ``function``\ s and ``macro``\s are in lower case, without
  underscores.
- Functions that modify their inputs have names that end in ``!``. These
  functions are sometimes called mutating functions or in-place functions.
