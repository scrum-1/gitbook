# Lua 程式關鍵字

and break do else elseif end false for function if in local nil not or repeat return then true until while 等 21 個

# Lua 註解

單行註解 --

多行註解 --\[\[    \]\]

# Lua 資料型別

nil, boolean, number , string, function, userdata, thread, 與 table 等八種資料, true 與 false 使用小寫, 與 Python 的 True 與 False 不同. 

Lua 允許使用 field name 作為 index. 因此可以用 a.name 來表示 r a\["name"\].

Tables, functions, 與 userdata values 為 objects: variables 並非實際內存這些 values, 而只透過參照指向這些 values.

# Chunks

可以循序執行的程式段, 在 Lua 中稱為大區塊

The unit of execution of Lua is called a chunk. A chunk is simply a sequence of statements, which are executed sequentially

The fact that a chunk is a block does not mean that any block is a chunk. Chunks do not nest \(unlike blocks\). A chunk is an outermost block which you feed to "load". A chunk is an independently executable sequence of statements. A block is just a sequence of statements. The difference is that a chunk can be executed independently of other chunks.

# Blocks

Lua 中的所謂區塊 \(blocks\) 指一系列的敘述 \(statements\), 能夠明確界定為單一敘述的程式範圍, 都可視為區塊.

區塊 \(blocks\) 則是大區塊 \(chunks\) 的一部分

區塊中可以透過 return 或 break 敘述在特定敘述句中跳到另外一個區塊中執行.

區塊範例:

while 

exp 

do block 

end



repeat 

block 

until exp 



if exp 

then block 

{ elseif exp then block } 

\[ else block \] 

end



