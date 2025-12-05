#eth 
(Extended Backus Naur/Normal Form)

**word** defined as a valid string
**language** defined as a set of valid strings

> [!Note]
> EBNF can be used in Parser


# Basics to EBNF

## Definition EBNF description

- A set of EBNF rules
- In the form $LHS \leftarrow RHS$ ("defined as")
	- LHS: \<name\>
	- RHS: 
		- Terminal (a character)
		- name of EBNF rules
		- Combination of control forms

## Example - "D0"

- <letter_D> $\longleftarrow$ D
- <digit_zero> $\longleftarrow$ 0
- \<room1\> $\longleftarrow$ \<letter_D\> <digit_zero>

same to 

- \<room1\> $\longleftarrow$ D 0

## Decision
- **selection**
	- \<digit\> $\longleftarrow$ 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
- **option**
	- \<sign\> $\longleftarrow$ + | -
	- \<number\> $\longleftarrow$ [\<sign\>] \<digit\>

## Repetition

any number of times
- \<sequence\> $\longleftarrow$ \<digit\> {\<digit\>}


## Example: Palindrome

- \<digits\> <= 1|2|3|4
- \<pal\> <= (1 \<pal\> 1) | (2 \<pal\> 2) | (3 \<pal\> 3) | (4 \<pal\> 4) | \<digits\>

