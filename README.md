# Lua + Faust playground

## faust-tpl
Faust wrapper similar to faust2xxx tool that pre-processes a .dsp containing `{{` and `}}` tags, enabling compile-time templating. Based on [etlua](https://github.com/leafo/etlua).
Examples:
```c
{{
	-- block of lua code, all blocks are evaluated in the same context, ie. define here and use later.
}}
```
Use `{{=` to use value of block, ie. variables, function return value: `abc = {{= def }};`

#### Usage
`faust-tpl [options] <file.dsp>` to process templated dsp file.dsp, all options except dsp files are passed to faust.  
The lua script can be called directly: `lua5.4 render_template.lua -o out_file in_file.dsp`