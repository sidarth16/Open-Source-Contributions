# 🔐 Open Source Contributions

<!-- A summary of my contributions to notable open-source security tools, with links to pull requests and summary of key improvements. -->

## Slither ([crytic-slither](https://github.com/crytic/slither))

- [Enhancement #2753](https://github.com/crytic/slither/pull/2753)  
*(feat: Add Function module to detect functions returning msg.sender directly or via alias*)<br/>
This PR introduces a new method `is_returning_msg_sender()` in the Function class, enabling detection of Solidity functions that return `msg.sender`, either directly or through transitive variable aliasing.
    - The newly added method `Function.is_returning_msg_sender()` returns True if:
        - The function directly returns `msg.sender` , 
        - The function returns a variable that was directly or transitively assigned from msg.sender


 - [Fixed Bug #2747](https://github.com/crytic/slither/pull/2748/)  
 Removes duplicate functions in ```get_msg_sender_checks``` to avoid repeated ```msg.sender``` condition nodes


 - [Enhancement #1722](https://github.com/crytic/slither/pull/1722)  
 This function would be helpful to de-register a detector class from the list of detectors already registered with the slither object

- [Enhancement #1724](https://github.com/crytic/slither/pull/1724)  
Un-Register a printer class from the list of printers already registered with the slither object.


- [#1705](https://github.com/crytic/slither/pull/1705)  [#2751](https://github.com/crytic/slither/pull/2751) ( *Fixed typo's* )
    - [#1705](https://github.com/crytic/slither/pull/1705) - misspelt msg.sender in the reentrancy-eth module
    -  [#2751](https://github.com/crytic/slither/pull/2751) - misspelt terms in function doc-strings


---

##  Cairo-Lang Book ([cairo-book](https://github.com/cairo-book/cairo-book))

-  [Issue #1191](https://github.com/cairo-book/cairo-book/pull/1191)   
Adds a note under the "Matching Tuples" section to clarify that match on tuples currently supports only enums as tuple members. Removes redundant match arms in quiz questions.

- [Issue #1190](https://github.com/crytic/slither/pull/1705)  
Fixed incorrect usage of function names in quiz.

