set number
syntax on
set tabstop=4
set softtabstop=4
set shiftwidth=4
set noexpandtab
set autoindent
set cindent

inoremap ( ()<ESC>i
inoremap [ []<ESC>i
inoremap { {}<ESC>i
inoremap " ""<ESC>i
inoremap ' ''<ESC>i



func SkipPair()  

    if getline('.')[col('.') - 1] == ')' || getline('.')[col('.') - 1] == ']' || getline('.')[col('.') - 1] == '}'  || getline('.')[col('.') - 1] == "'" || getline('.')[col('.') - 1] == '"'

        return "\<ESC>la"  

    else  

        return "\t"  

    endif  

endfunc  

func SkipPair2()  

    if getline('.')[col('.') - 1] == '}'  

        return "\<CR>\<ESC>O"  

    else  

        return "\<CR>"  

    endif  

endfunc  


inoremap <TAB> <c-r>=SkipPair()<CR>
inoremap <CR> <c-r>=SkipPair2()<CR>
