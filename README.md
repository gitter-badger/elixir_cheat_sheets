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

              