1.  In a script, initialize an array (that has length == 3) of your favourite people, represented as `String`s, and `log` it.
![[Pasted image 20221117202707.png]]
    
2.  In a script, initialize a dictionary that maps the `String`s Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a `UInt64` that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!
![[Pasted image 20221117202810.png]]
3.  Explain what the force unwrap operator `!` does, with an example different from the one I showed you (you can just change the type).
	1. As far as i understand, it forces you to have a type, so that it can't be nil
    
4.  Using this picture below, explain...
    
    -   What the error message means
	    - The return type is set to "String" but it gets a "String?". This is because a library returns it's value as an optional.
    -   Why we're getting this error
	    - because the return type is set to "String"
    -   How to fix it
	    - Change the return type to "String?" or add an ! to your return, so that it is forced-unwrapped 