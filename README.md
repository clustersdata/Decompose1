# Decompose1

Decompose1

把自然数Ｎ分解为若干个自然数之积。

【参考程序】

var  path :array[1..1000] of integer;

     total,n:integer;
     
procedure find(k,sum,dep:integer);	 {K:}

var b,d:Integer;

begin

     if sum=n then		     {积等于N}
     
      begin
      
	write(n,'=',path[1]);
  
  
	for d:=2 to dep-1 do write('*',path[d]);
  
	writeln;inc(total);
  
	exit;
  
      end;
      
    if sum>n then exit; 		{累积大于N}
    
    for b:= trunc(n/sum)+1 downto k do	{每一种可能都去试}
    
	begin
  
	       path[dep]:=b;
         
	       find(b,sum*b,dep+1);
         
	end;
  
end;


begin

readln(n); total:=0;

find(2,1,1);writeln('total:',total);

readln;

end.
