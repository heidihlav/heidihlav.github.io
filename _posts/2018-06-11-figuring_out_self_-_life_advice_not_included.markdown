---
layout: post
title:      "Figuring out self - Life advice not included."
date:       2018-06-11 21:42:57 -0400
permalink:  figuring_out_self_-_life_advice_not_included
---

As I approach my first project for the Ruby: OO section, there is one really foundational concept that remains the most difficult for me to internalize. And that is the concept of "self" in relation to classes, instances and their methods. While I may still be reading up on it and practicing with it, I hope to give another new OO programmer some clarity on the subject by sharing what I've learned so far. 

**Self has a context**

You can't figure out who self is and when to use self without considering its environment. I'll explain by metaphor. 
I have two cats. The female cat, Medea, has amber eyes, and the male cat, Bhindi has green eyes. Medea is a spotted tabby, and Bhindi is a swirled tabby. Bhindi likes to nap and Medea likes to bat around her jingly ball. I'm going to make Medea and Bhindi and give them their favorite activities to do. Then we can talk about who is "self" in the code below.

In code form:

```

class Cat

        attr_accessor :eyes, :fur, :sex, :name
				
				def initialize(eyes, fur, sex, name)
					@name = name
					@eyes = eyes
					@fur = fur
					@sex = sex
				end
				
				def take_nap
				    puts "#{name} wants to sleep on my keyboard."
				end
				
				def play
				    puts "#{name} got her jingly ball stuck under the fridge."
				end
				
			end
			
			```
			
If I make a Bhindi and a Medea, (```Bhindi = Cat.new()```) I can tell them to do their favorite activities. ```Bhindi.take_nap => "Bhindi wants to sleep on my keyboard."``` In the two activity methods above, "self" would be the *instance*  of cat, or the cat who I call to do the activity. The instance Bhindi would be the explicit receiver of #take_nap, but "Self" is the implicit receiver of #take_nap. Which leads me to my favorite and easiest to remember clue as to who is "self" in a method.

**If you put "self." in the method definition, the class is "self" in that method. If you don't, it's an instance method, and the instance itself is "self."**

If I wanted to make more cats (Make allll the cats!!) I would ask the class Cat to keep track of the cats I've made. So I would build ```self.all => @@all = [Bhindi object, Medea object, etc]``` which would give me an array of all the cats I've made. "Self" for that method is the Cat class. 

This is what I've picked up so far working on Ruby OO labs that use classes. The idea of "self" changing depending on its environment is pretty confusing at first, but there are a lot of resources that you can use to understand it better. Aside from the labs, here are two articles that helped me:

["Three Golden Rules to Understand Self in Ruby"](https://hackhands.com/three-golden-rules-understand-self-ruby/)

["Understanding 'self' in Ruby"](http://blog.honeybadger.io/ruby-self-cheat-sheet/)




			
			
			
			
			


