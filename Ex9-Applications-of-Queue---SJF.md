# Ex9 Applications of Queue - SJF
## DATE:
## AIM:
To incorporate the code to calculate the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm.
## Algorithm
1. Start and read number of processes n and their burst times in bt[]; assign process IDs in p[].
2. Sort bt[] and p[] using selection sort based on burst time.
3. Compute waiting time wt[] by summing previous burst times.
4. Calculate turnaround time tat[] = bt[] + wt[] for each process.
5. Print average waiting time and turnaround time, then end.

## Program:
```
/*
Program to find the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm.
Developed by: vinodhini k
RegisterNumber:  212223230245
*/
#include<stdio.h>
int main()
{
int bt[20],p[20],wt[20],tat[20],i,j,n,total=0,pos,temp;
float avg_wt,avg_tat;
scanf("%d",&n);
for(i=0;i<n;i++)
{
scanf("%d",&bt[i]);
p[i]=i+1;
}
for(i=0;i<n;i++)
{
pos=i;
for(j=i+1;j<n;j++)
{
if(bt[j]<bt[pos])
pos=j;
}
temp=bt[i];
bt[i]=bt[pos];
bt[pos]=temp;
temp=p[i];
p[i]=p[pos];
p[pos]=temp;
}
wt[0]=0;
for(i=1;i<n;i++)
{
wt[i]=0;
for(j=0;j<i;j++)
wt[i]+=bt[j];
total+=wt[i];
}
avg_wt=(float)total/n;
total=0;
printf("Process BurstTime WaitingTime TurnaroundTime\n");
for(i=0;i<n;i++)
{
tat[i]=bt[i]+wt[i]; //calculateturnaroundtime
total+=tat[i];
//printf("\n");
printf("p%d %d %d %d\n",p[i],bt[i],wt[i],tat[i]);
}
avg_tat=(float)total/n; //average turnaroundtime
//printf("\n");
printf("AverageWaitingTime=%f\n",avg_wt);
// printf("\n");
printf("AverageTurnaroundTime=%f\n",avg_tat);
return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/942c1af0-6ed8-43b8-b333-a09ad0506b42)


## Result:
Thus, the code to calculate the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm is implemented successfully.
