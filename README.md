# elixir_cheat_sheets
Uncommon Logical stuff of Elixir modules,definitions and some coding snippets that makes our life easy.         
###1 :Creating Private Functions
######Code
```elixir
defp defname (variables) do
    //your definition goes here 
end
```
######Example
```elixir
defmodule Mymodule do
@doc This is the public function can be called out side
    def public_function() do 
        IO.puts "I am a public function"
    end 
    defp private_function() do
        IO.puts "I am private function"
    end
end
```
######Description   
Here `defp` stands for the private function which means you cannot call that function out side module by importing like this `Mymodule.private_function`.This can be used only inside the another functions in the module it has been defined in our example it can be called inside the `public_function`          


###2 :Pipe Operations `|>'
######Code
```elixir
getName id |> toUpperCase
```
######Example
```elixir
defmodule myModule do
    def function() do
        admin = getNameById id |> toUpperCase |> isAdmin
        IO.puts admin
    end
end

```
######Description   
here the out put of the `getNameByID` is passed as the first parameter to the `toUpperCase` in which it returns name as all capitals letters and that name is passed to the `isAdmin` function to check that the person is admin or not finally a `boolean` `true` or `false` is returned.                  
The Overall function chain  goes like this                   
```javascript
getNameById(id).toUpperCase().isAdmin()
```      

###3 :import specific functions
######Code
```elixir
import :math, only: [sqrt: 1]
import :math, except: [sin: 1, cos: 1]
```
######Example
```elixir
import :math, only; [sqrt: 1]
defmodule myModule do
    def function() do
        sqrt 4
    end
end
```
######Description   
In the above example it loads or imports only the sqrt function in to the module.So you no need access the function with the module name `:math.sqrt 4` you can directly call them with `sqrt 4`.How ever you can make use of othe functions like this because you are saying to import only specific functions.      
###4 :Default values Functions
######Code
```elixir
def fall_velocity(distance, gracity \\ 9.8) do
    //code
end
```
######Example
```elixir
import :math, only: [sqrt: 1]
defmodule myModule do
    def fall_velocity(distance, gravity \\ 9.8) do
        velocity=sqrt 2*gravity*distance
        IO.puts "the falling velocity is #{velocity}"
    end
end
```
######Description   
In the above code the `fall_velocity` function takes two params one is `distance` and another is `gravity` if you pass only one param then the `gravity` value is default is set to the `9.8` here you need to give blank space between `gravity` and `\\` and `9.8`            

###5 :Documentation and specifications
######Code
```elixir
defmodule myModule do
@moduledoc """
Explanation about the module
""
@vsn 0.1 -- moduel version
@doc """
your documentation here can have multiple 
lines of text 
line 1
line 2 
etc
"""
@spec functionName(number()) :: number()
    def functionName() do
        //code
    end
end
```
######How to use?
```elixir
h(moduleName.functionName)
s(modulename.functionName)
```
######Description   
Here `h()` stands for help when you type like that you will be displayed with the `@doc` text and similarly when you type `s()` you will be getting the function specifications it explains what parameters has to pass and what it returns when you call or simply what has to give to the function and what it will give in return.          


###6 :Using Erlang From Elixir
 ######Code
 ```elixir
 :application.which_applications
 :erlang.module_info
 ```
 ######Description   
 here the `list_applications` returns the list of applications being executed in an Erlang VM .This is the way to use the function from Elixir.         
 The erlang would be like this           
```
application:which_applications()     -- moduleName:functionName() 
```

###7 :Observer GUI
######Code
```elixir
:observer.start
```
["observer.image"]('./assets/observer_chart.png')
