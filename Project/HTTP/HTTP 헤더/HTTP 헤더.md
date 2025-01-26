# 구조적 설명
header-field = field-name ":" [[OWS]] field-value OWS 

field-name = token 
field-value = *( field-content / [[obs-fold]] ) 
field-content = field-vchar [ 1*( SP / HTAB ) field-vchar ] 
field-vchar = VCHAR / obs-text 

obs-fold = [[CRLF]] 1*( [[Single Space|SP]] / [[HT|HTAB]] ) 
        ; obsolete line folding ; see Section 3.2.4

# 논리적 설명