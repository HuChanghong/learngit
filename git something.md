<!-- MarkdownTOC autolink="true" autoanchor="true" -->

- [warning](#warning)
	- [warning: LF will be replaced by CRLF](#warning-lf-will-be-replaced-by-crlf)

<!-- /MarkdownTOC -->
这里用来记录一些使用Git时遇到的问题;  
因为百度和谷歌能完全解决,所以这里只是记录一下要点,不做详述;  

<a id="warning"></a>
## warning
<a id="warning-lf-will-be-replaced-by-crlf"></a>
### warning: LF will be replaced by CRLF
1. #提交时转换为LF，检出时转换为CRLF  
`$ git config --global core.autocrlf true` 适用于Window
2. #提交时转换为LF，检出时不转换  
`$ git config --global core.autocrlf input`适用于MAC/Linux
3. #提交检出均不转换  
`$ git config --global core.autocrlf false`仅用于Window
4. #在文件提交时进行safecrlf检查  
	* #拒绝提交包含混合换行符的文件  
	`git config --global core.safecrlf true` 
	* #允许提交包含混合换行符的文件  
	`git config --global core.safecrlf false`
	* #提交包含混合换行符的文件时给出警告  
	`git config --global core.safecrlf warn`

关于换行符  
\r == CR == Carriage Return (回车return)  
\n == LF == Line Feed       (换行newline)  
  
|操作系统|换行符|
|---|---|
|Windows|CRLF|
|MAC/LINUX/UNIX|LF|
  
>早期的MAC OS是CR,后来的OS X在更换内核后和UNIX一样也是LF
