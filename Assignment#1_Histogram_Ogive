"""
Created on Tue Aug 25 13:17:10 2020

@author: Ahmed Issa
"""
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

print("Enter Data Set : ")
data = list(map(int, input().split()))
print(80*"#")
      
N = len(data)
print("Sorted Data Set :", sorted(data))
print("\nData Length :", N)

k = 0
while (2**k <= N):
    k = k + 1
print("Number of Classes (K):",k)

largestVal = max(data)
#print("max :", largestVal)
smallestVal = min(data)
#print("min :", smallestVal)

w = int(np.ceil((largestVal - smallestVal) / k))
print("CLass Width (W) :", w)
print(80*"#")
      
start = min(data)
table = []
startList = []
ct = 0
cumulative = 0
cumList = [0]
totF = 0
totRel = 0
for i in range(k):
    end = start + w
    for j in range(N):
        if(data[j] >= start and data[j] < end):
            ct = ct + 1
    
    startList.append(start)
    freq  = ct
    totF = totF + freq
    
    relative = freq / N
    totRel = totRel + relative
    
    cumulative = cumulative + relative
    cumList.append(cumulative)
    
    table.append([start,end,freq,relative,cumulative])
    start = end
    ct = 0

#print(table)
startList.append(start)
table.append(['====','====','====','====','===='])
table.append(['','Total',totF,totRel,' '])
df = pd.DataFrame(table, columns = ['Start','End', 'Freq','Relative','Cumulative']) 
print(df)
print(80*"#")
      
#print(startList)
#print(cumList)
plt.hist(data,bins = startList)
plt.ylabel('Frequency')
plt.xlabel('Data')
plt.title("Histogram")
plt.show()

plt.plot(startList,cumList,marker='o')
plt.ylabel('Frequency')
plt.xlabel('Data')
plt.title("Ogives")
plt.show()
