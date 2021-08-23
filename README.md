##Python program using Dictionaries:

import json
MusicFestival={
    "Omega festival":{"Band X":"RecordLabel1"},
    "":{"Band Y":"RecordLabel1"},
    "Alpha festival":{"Band A":"RecordLabel2"},
    "Beta festival":{"Band A":"RecordLabel2"}
}
Band={
    "Band X":"RecordLabel1",
    "Band Y":"RecordLabel1",
    "Band A":"RecordLabel2"
}    
newlist=[]
for k,v in Music.items():
    if(type(v)) is dict:
        for t,c in v.items():
          rec=c
          band=t
          festival=k
          newlist.append(c+" "+t+" "+k )
         
newlist.sort()          
print(newlist) 

##Java Program using HashMap:

import java.util.HashMap;
import java.util.ArrayList;
import java.util.Collections;
public class Main {
    public static void main(String[] args) {
        HashMap<String,String> Music= new HashMap<String,String>();
        HashMap<String,String> Band=new HashMap<String,String>();
        Music.put("omega festival","Band X");
        Music.put("Alpha festival","Band A");
        Music.put("Beta festival","Band A");
        Music.put("","Band Y");
        Band.put("Band X","recordLabel1");
        Band.put("Band Y","recordLabel1");
        Band.put("Band A","recordLabel2");
        for(String i:Music.values())
        {
            for(String j:Band.keySet())
            {
                for(String k:Music.keySet())
                {
                    for(String l:Band.values())
                    {
                        if(i==j)
                        {
                          System.out.println(l);
                          System.out.println(j);
                          System.out.println(k);
                        }
                    }    
                }
            }
            
        }
      
    }
}

##Python program using class:

import json
from typing import NamedTuple
from operator import attrgetter
def multi_sort(data,specs):
    for key,reverse in reversed(specs):
        data.sort(key=attrgetter(key),reverse=reverse)
    return data
class Music(NamedTuple):
      festival:str
      band:str
      RecordLabel:str

m1=Music('omega festival','Band X','RecordLabel1')
m2=Music('','Band Y','RecordLabel1')
m3=Music('Alpha festival','Band A','RecordLabel2')
m4=Music('Beta festival','Band A','RecordLabel2')
 
Musics=[m1,m2,m3,m4]
multi_sort(Musics,(('RecordLabel',False),('band',False),('festival',False)))
for Music in Musics:
    print(Music)
