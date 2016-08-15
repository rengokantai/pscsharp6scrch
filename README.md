#### pscsharp6scrch
######31 polymorphism
```
class Book{
  public virtual double Met();
}
class Sub: Book{
public override double Met(){
  base.Met();
}
}

```
######33 Objects
```
namespace C
{
  public double H{get;set;}
  public C(string name,double h)
  :base(name)
  {
    H=h;
  }
}
```

######53 Delegates (re-read the codes; subscribe the event)
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
######61 LINQ demo
```
var listInt = new List<int>{1,2,3};
var smallnum = from num in listInt where num <2 select num;

foreach(int number in smallnum){
  
}
//lambda
var smallnum = listInt.Where(n=>n<2).Select(n=>n);
```
######63 query methods
```
from moethod in typeof(int).GetMethods() orderby method.Name group method by method.Name into groups
select new
{
  MethodName = groups.Key,
  MethodOverloads = groups.Count()
};
```
#######64 Deferred
```
var deferred = Enumberable.Range(0,100).Select(x=>
{
Thread.sleep(500);
return x*x;
}
```
######65 Operators
```
Any
Take
Distinct
Zip
```
######66 Any
```
bool res = list.Any();
bool res = list.Any(x=>x==2);
```
######67 Take
```
var l= list.Take(5).Select(x=>x>2);
```
######68 Distinct
remove duplicates
######69 Zip
```
var a =new List<string>{"A","B"};
var b =new List<string>{"C","D"};
var c = a.Zip(b,(x,y)=>$"{x},{y}");
```
