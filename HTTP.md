[toc]

## HEADER
### content-disposition
用于指定浏览器打开或者下载文档

[参考](https://httpwg.org/specs/rfc6266.html)
> 19.5.1 Content-Disposition
>   The Content-Disposition response-header field has been proposed as a
>   means for the origin server to suggest a default filename if the user
>   requests that the content is saved to a file. This usage is derived
>   from the definition of Content-Disposition in RFC 1806 [35].
>
>        content-disposition = "Content-Disposition" ":"
>                              disposition-type *( ";" disposition-parm )
>        disposition-type = "attachment" | disp-extension-token
>        disposition-parm = filename-parm | disp-extension-parm
>        filename-parm = "filename" "=" quoted-string
>        disp-extension-token = token
>        disp-extension-parm = token "=" ( token | quoted-string )
>
>   An example is
>
>        Content-Disposition: attachment; filename="fname.ext"
>
>   The receiving user agent SHOULD NOT respect any directory path
>   information present in the filename-parm parameter, which is the only
>   parameter believed to apply to HTTP implementations at this time. The
>   filename SHOULD be treated as a terminal component only.
>
>   If this header is used in a response with the application/octet-
>   stream content-type, the implied suggestion is that the user agent
>   should not display the response, but directly enter a `save response
>   as...' dialog.
>
>   See section 15.5 for Content-Disposition security issues.


- 遗留问题： filename 设置为特殊字符*|/\<>时，chrome自动下载会变成下划线？