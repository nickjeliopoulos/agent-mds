---
name: remind-pystyle
description: A style reminder when creating Python code. Used to enforce user style preferences for Python code, and detecting non-runtime errors.
disable-model-invocation: false
---
# TRIGGER 
Writing new Python code, especially large codebase update
 - Request 100+ line edit or new, non-trivial Python code
 - Request integration of code from different style
 - Writing code in new project

# ACTION
Consider the following set of rules when writing code
#GENERAL
 - Docstring at top of file with basic description and command line usage
 - Large sections of code prefixed by comment like:
 ```
 ###
 ### Helpers
 ###
 ...
 ```
 - Comment formatting like `### <comment>`
 - Function-specific docstring if sufficiently complicated
 - No whitespace or tab to align code, unless deemed highly important
 - 2 spaces between the start and end of functions

 #ARGPARSE
  - No `help=` unless explicitly requested

#PYTORCH
  - Do not decorate individual functions with `torch.compile(...)`

 # VERIFICATION
If large amount of code was written, invoke `scripts/ast.sh <file>` to verify