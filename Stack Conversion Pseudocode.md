Infix to Postfix
function infixToPostfix(expression):
    create empty stack
    result = ""

    for each character ch in expression:
        if ch is operand:
            add ch to result

        else if ch == '(':
            push ch to stack

        else if ch == ')':
            while top of stack != '(':
                pop from stack and add to result
            pop '('

        else if ch is operator:
            while stack not empty AND precedence(top) >= precedence(ch):
                pop from stack and add to result
            push ch to stack

    while stack not empty:
        pop from stack and add to result

    return result
Infix to Prefix

function infixToPrefix(expression):
    reverse expression

    for each character:
        if '(' → replace with ')'
        if ')' → replace with '('

    postfix = infixToPostfix(expression)

    return reverse(postfix)
