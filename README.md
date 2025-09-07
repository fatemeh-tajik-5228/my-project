#project_1
#include <iostream>
using namespace std ;
// mohasebe Rn
int main () {
	int n , power ;
	cout << "Andaze matris ra vared kon(satr=sotoon) : " ;
	cin >> n ;
	int A[n][n] , result[n][n] , temp[n][n] ;
	cout << "matris rabeteh ra vared kon(0 or 1) :\n" ;
	for(int i=0 ; i<n ; i++) {
		cout << "satr" << i+1 << ": " ;
		for(int j=0 ; j<n ; j++) {
			cin >> A[i][j] ;
			result[i][j] = A[i][j] ;
    	}
	}
	cout << "\n" ;
	cout << "tavan: " ;
	cin >> power ;
	
	for(int p=0 ; p<power ; p++) {
		for(int i=0 ; i<n ; i++) {
			for(int j=0 ; j<n ; j++) {
				temp[i][j] = result[i][j] ;
				result[i][j] = 0 ;
			}
		}
	for(int i=0 ; i<n ; i++) {
		for(int j=0 ; j<n ; j++) {
			for(int k=0 ; k<n ; k++) {
				result[i][j] = result[i][j] || (temp[i][k] && A[k][j]) ;
			}
		}
	}
    }
	cout << "\nmatris R^" << power << ":\n" ;
	for(int i=0 ; i<n ; i++) {
		for(int j=0 ; j<n ; j++) {
			cout << result[i][j] << "  " ;
		}
		cout << "\n" ;
	}
	return 0 ;
}
