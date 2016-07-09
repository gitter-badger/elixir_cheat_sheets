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

---          
Here `defp` stands for the private function which means you cannot call that function out side module by importing like this `Mymodule.private_function`.This can be used only inside the another functions in the module it has been defined in our example it can be called inside the `public_function`
---              
