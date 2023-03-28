Operator=set(['+','-','*','/','(',')','^'])    
Priority={'+':1,'-':1,'*':2,'/':2,'^':3}     

def InfixToPostfix(expression):
	stack=[]		
	output=" "

	for character in expression:
		if character not in Operator:	
			output+=character
		elif character=='(':			
			stack.append('(')
		elif character==')':
			while stack and stack[-1]!='(':
				output+=stack.pop()
		else:
			while stack and stack[-1]!='(' and Priority[character]<=Priority[stack[-1]]:
				output+=stack.pop()
			stack.append(character)
	while stack:
		output+=stack.pop()
	return output

#Main
a='4*3'
print(InfixToPostfix(a))


