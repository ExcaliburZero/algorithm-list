# Heap's Algorithm
Heap's Algorithm is an algorithm used for creating combinations of given inputs. Such inputs are generally given as an array of elements. The outputs given are each possible permutation of the given array with no duplicate permutations.

## Example
``` Java
/**                                                                             
 * The method used to generate all of the possible permutations of the          
 * numbers 1 through n.                                                         
 *                                                                              
 * @param n The number of numbers to create permutations of                     
 * @param a The array of numbers 1 through n                                    
 */                                                                             
public static void generate(int n, int[] a) {                                   
        // Placeholder for swapping values                                      
        int tmp;                                                                
        // If a new permutation has been found then print it                    
        if(n == 1) {                                                            
                // Print out the found permutation                              
                for(int i = 0; i < a.length; i++) {                             
                        System.out.print(a[i]);                                 
                }                                                               
                System.out.println();                                           
        }                                                                       
        else {  // If a new permutation has not yet been found                  
                for(int i = 0; i < (n-1); i++) {                                
                        generate(n-1, a);                                       
                        if(n % 2 == 0) {                                        
                                // Swap entry i with entry n-1                  
                                tmp = a[i];                                     
                                a[i] = a[n-1];                                  
                                a[n-1] = tmp;                                   
                        }                                                       
                        else {                                                  
                                // Swap entry 0 with entry n-1                  
                                tmp = a[0];                                     
                                a[0] = a[n-1];                                  
                                a[n-1] = tmp;                                   
                        }                                                       
                }                                                               
                generate(n-1, a);                                               
        }                                                                       
} 
```
