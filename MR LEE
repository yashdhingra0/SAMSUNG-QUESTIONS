#include<iostream>
#include<climits>
using namespace std;

int N, result;

void minCostMrLee(int **arr, bool *visited, int count, int cost, int src){
    // Base Case
    if(count == N-1){
    	/* Corner Case if no path exists from last city */
        if(arr[src][0] != 0)
        	result = min(result, cost + arr[src][0]);
        return;
    }
    
    // Main Case
    for(int i=0; i<N; i++){
        if(!visited[i] && arr[src][i] != 0){
            visited[i] = true;
            minCostMrLee(arr, visited, count + 1, cost + arr[src][i], i);
            visited[i] = false;
        }
    }
}

int main(){
	int t;
	cin >> t;
	while(t--){
		cin >> N;
		int **arr = new int*[N];
		for(int i=0; i<N; i++){
			arr[i] = new int[N];
		}
        bool *visited = new bool[N];
		
        for(int i=0; i<N; i++){
            visited[i] = false;
			for(int j=0; j<N; j++){
				cin >> arr[i][j];
			}
		}
		
        result = INT_MAX;    
        
        visited[0] = true;
        
        minCostMrLee(arr, visited, 0, 0, 0);
        result != INT_MAX ? cout << result << "\n" : cout << "-1\n";
	}
	return 0;
}
