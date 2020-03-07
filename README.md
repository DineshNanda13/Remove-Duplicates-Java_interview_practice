# Remove-Duplicates-Java_interview_practice
Java program to remove duplicates in an array

package remove_Duplicates;

/**
 *
 * @author Dinesh Nanda
 */

public class Remove_Duplicates {
    
    public int[] asc_order(int[]list){
        
        for (int i = 0; i < list.length; i++) {
            for (int j = i + 1; j < list.length; j++) {

                if (list[i] > list[j]) {

                    int temp = list[i];
                    list[i] = list[j];
                    list[j] = temp;
                }
            }  
        }
        return list;
    } 
    
    public int duplicates(int [] list, int size){
        
        if(size <= 1){
            return size;
        }
        int j = 0;
        
        //Overriding the array
        
        for(int i = 0; i < list.length - 1; i++){
            
            if(list[i] != list[i+1]){
                list[j] = list[i];
                j++;
            }
        }
        list[j] =  list[list.length - 1];
        j++;
        return j;
    }
    
    public static void main(String[] args) {
     
        int arr[] = {30, 20, 50, 30, 10, 40, 50, 20};
        
        Remove_Duplicates d = new Remove_Duplicates();
        
        arr = d.asc_order(arr); //Ascending
        
        int total_length = d.duplicates(arr, arr.length); //Duplicates
        
        for(int i = 0; i < total_length; i++){
            
            System.out.print(arr[i]+" ");
        }
    }   
}
