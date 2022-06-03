# TenLinesSnake
A snake in ten lines of code | C# Console
```c#
        static void Main(string[] args)
        {
            Task.Delay(1000 / 15).Wait();
            G.D=Enumerable.Range(0,G.H).Select(w=>new char[G.W].Select(cH=>'.').ToArray()).ToList();
            new Action<char>(s=>G.O=s=='a'?0:s=='w'?1:s=='d'?2:s=='s'?3:G.O).Invoke(Console.KeyAvailable?Console.ReadKey(true).KeyChar:' ');
            G.M.ForEach(c=>G.D[c.Y>=0?c.Y%G.H:((G.H+(c.Y%G.H))%G.H)][c.X>=0?c.X%G.W:((G.W+(c.X%G.W))%G.W)]='%');
            G.M.Select((t,i)=>G.M.Count()-1-i).ToList().ForEach(i=>G.M[i]=i!=0?G.M[i-1]:(G.P=G.O==0?(G.P.X-1,G.P.Y):G.O==1?(G.P.X,G.P.Y-1):G.O==2?(G.P.X+1,G.P.Y):(G.P.X,G.P.Y+1)));
            (G.A=G.T++%10==0?Enumerable.Union(G.A,new List<(int X, int Y)>(){(G.R.Next(0,G.W),G.R.Next(0,G.H))}).ToList():G.A).ForEach(c=>G.D[c.Y][c.X]='A');
            G.M=G.A.Any(a=>a==G.P)?Enumerable.Append(G.M,(0,0)).ToList():G.M;
            G.A.Select((t,i)=>(t,i)).ToList().ForEach(e=>G.A=G.A.Where(a=>a!=G.P).ToList());
            new Func<Task>(async()=>Console.Clear()).Invoke().ContinueWith(t=>Console.WriteLine(string.Join("",G.D.Select(chs=>new string(chs)+"\n"))));
            new Action((G.P.X<0||G.P.X>=G.W||G.P.Y<0||G.P.Y>=G.H||G.M.Skip(1).Contains(G.P))?new Action(()=>{}):new Action(()=>Main(null))).Invoke();;
        }
```
