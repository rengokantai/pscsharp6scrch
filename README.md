#### pscsharp6scrch
######53 Delegates
declare delegate
```
public class Media{
  public delegate bool TestMedia();
```

create a method use delegate
```
public void TestResult(TestMedia m){
if(m()==true)
{
  ...
}
}
```

another usage
```
public bool test(){
  return false;
}

TestMedia t = new TestMedia(test);
```
######59 Lambda expression
```
public void Work()
{
  int a =10;
  int b =20;
  Func<int, int, int> mul;
  mul=Multiply;
  int prod = mul(a,b);
  //lambda: Func<int,int,int> mul2 = (x,y)=>(x*y);
}

public int Multiply(int x,int y){
  return x*y;
}
```
