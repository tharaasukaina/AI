def dls(graph,goal,limit):
  root=list(graph.keys())[0]
  s,temp,visited,path=[(root,1)],[],[],[]
  parent ={root:None}
  while s:
    
    v,d=s.pop()
    if v==goal:
       while parent[goal]:# ما دام البيرنت اللي الا موجود  يعني انا ما وصلت         
          path.insert(0,goal)
          goal=parent[goal]
       path.insert(0,root)
       break
    visited.append(v)
    for i in graph.get(v,[]):
       if i not in visited and d<limit :
          temp.append(i)
          parent[i]=v#تعريف البيرنت
    while temp :
       s.append((temp.pop(),d+1))
  return path,visited


#graph={1:[2,3],2:[5,6],3:[7,8],4:[],5:[9],6:[10],9:[12],12:[],10:[],7:[],8:[4]}

graph ={1:[2,3] ,2:[5,6],3:[7,8],5:[9],6:[2,5],7:[2,4],8:[10]} #direction graph 
goal,limit = 7,3
path,visited=dls(graph, goal,limit)
if path:
    print("found goal  path :",path,"and visited node :",visited,sep=" ",end="*^^*")
else:
    print("goal not found")

