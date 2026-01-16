# Open Source Contributions

<!-- A summary of my contributions to notable open-source security tools, with links to pull requests and summary of key improvements. -->

## My PyPI Package
- [Solderx](https://github.com/sidarth16/SolderX) 
    - **SolderX** is a developer-first, all-in-one Solidity flattener that handles files, folders, and verified contracts from various Explorers— all on-the-fly. 
    - It features robust import resolutions, advanced remapping support, SPDX unification, topological sorting, import deduplication & cyclic dependency detection.
    -  PyPI link : pypi.org/project/solderx/

---


## Halmos ([a16z-halmos](https://github.com/a16z/halmos))
- [Enhancement:`#576`](https://github.com/a16z/halmos/pull/576)  
*(Enhance `div_xy_y` to support signed and unsigned division simplification)*  
This PR updates the div_xy_y helper to handle simplifications for both unsigned (`DIV`) and signed (`SDIV`) EVM operations.
It allows expressions like `(x * y) / x` or `(x * y) / y` to be simplified automatically, improving symbolic reasoning and reducing complexity in arithmetic analysis.
---

## Slither ([crytic-slither](https://github.com/crytic/slither))
- [Enhancement:`#2867`](https://github.com/crytic/slither/pull/2867)  
*(feat: Add detector for `msg.value` usage unreachable from payable entry points*)<br/>
This PR resolves introduces a new Slither detector, `msg-value-in-nonpayable`, which identifies uses of `msg.value` in functions that can never be reached from any payable public or external entry point.<br/>
In such cases, `msg.value` is provably meaningless:
    - it is always zero, or
    - execution always reverts .
This detector helps developers catch logic errors, dead code, and incorrect assumptions about ETH flow early.

- [Enhancement:`#2753`](https://github.com/crytic/slither/pull/2753)  
*(feat: Add Function module to detect functions returning msg.sender directly or via alias*)<br/>
This PR introduces a new method `is_returning_msg_sender()` in the Function class, enabling detection of Solidity functions that return `msg.sender`, either directly or through transitive variable aliasing.
    - The newly added method `Function.is_returning_msg_sender()` returns True if:
        - The function directly returns `msg.sender` , 
        - The function returns a variable that was directly or transitively assigned from msg.sender


 - [Fix Bug:`#2747`](https://github.com/crytic/slither/pull/2748/)  
 Updates the logic in ```get_msg_sender_checks()```, removing duplicates & repeated ```msg.sender``` condition nodes


 - [Enhancement:`#1722`](https://github.com/crytic/slither/pull/1722)  
 Adds function that would be helpful to de-register a detector class from the list of detectors already registered with the slither object

- [Enhancement:`#1724`](https://github.com/crytic/slither/pull/1724)  
Adds a function that Un-Register a printer class from the list of printers already registered with the slither object.


- Fix Typos : [`#1705`](https://github.com/crytic/slither/pull/1705) , [`#2751`](https://github.com/crytic/slither/pull/2751) ( *Fix typo's* )
    - [`#1705`](https://github.com/crytic/slither/pull/1705) - misspelt ```msg.sender``` in the reentrancy-eth module
    -  [`#2751`](https://github.com/crytic/slither/pull/2751) - misspelt terms in function doc-strings


---

## Compose ([Perfect Abstractions-Compose](https://github.com/Perfect-Abstractions/Compose))
- [Fix:`#159`](https://github.com/Perfect-Abstractions/Compose/pull/160)  
*(`LibERC721Enumerable.sol` now set token owner during mint to resolve missing ownership)*  
This pull request fixes [#159] — the bug where `LibERC721Enumerable.mint()` did not assign ownership for newly minted tokens. Without this assignment, the token appeared non-existent (`ownerOf[tokenId] == address(0)`), causing transferFrom and burn to revert.
---

##  Cairo-Lang Book ([cairo-book](https://github.com/cairo-book/cairo-book))

- [Enhancement:`#1201`](https://github.com/cairo-book/cairo-book/pull/1201) : Fix test run inconsistencies and output mismatches in (`ch10_01`)
    - Fixes inconsistencies in test cases sections of `assert!`, `assert_eq!`, `assert_ne!`, `#[should_panic]`, `#[ignore]` Macros and section of : Running Single Tests 
    - Adds missing testcases in the contracts and fixes output logs as expected behaviour

- [Enhancement:`#1193`](https://github.com/cairo-book/cairo-book/pull/1193)  
    - Adds note on multiple derivable traits on structs

-  [Enhancement:`#1191`](https://github.com/cairo-book/cairo-book/pull/1191) : Tuple Matching Only Supports Enums (`ch06-04`)  
    - Issue: The "Matching Tuples" section implies that all tuple types can be used in match, but tuples with primitive types like (u8, u8) cause a compile-time error.

    - Fix: Add a note/text clarification that tuple matching currently supports only enums.

- [Issue `#1192`](https://github.com/cairo-book/cairo-book/pull/1192)  
Rephrase generics example sentence for clarity

- [Issue `#1190`](https://github.com/cairo-book/cairo-book/pull/1190)  
Fix incorrect usage of function names in quiz.

