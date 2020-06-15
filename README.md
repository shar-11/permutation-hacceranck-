# permutation-hacceranck-
  Class permutation
{

    public static boolean solve(String n, int l) 

    { 

        if (l < 3)  

        { 

            if (Integer.parseInt(n) % 8 == 0) 

                return true;

            n = new String((new StringBuilder()).append(n).reverse()); 

              

            if (Integer.parseInt(n) % 8 == 0) 

                return true; 

            return false; 

        }

        int []hash = new int[10]; 

        for (int i = 0; i < l; i++) 

            hash[n.charAt(i) - '0']++;



        for (int i = 104; i < 1000; i += 8)  

        { 

            int dup = i; 


            int []freq = new int[10]; 

            freq[dup % 10]++; 

            dup = dup / 10; 

            freq[dup % 10]++; 

            dup = dup / 10; 

            freq[dup % 10]++; 

      

            dup = i;

            if (freq[dup % 10] >  

                hash[dup % 10]) 

                continue; 

            dup = dup / 10; 

      

            if (freq[dup % 10] >  

                hash[dup % 10]) 

                continue; 

            dup = dup / 10; 

      

            if (freq[dup % 10] >  

                hash[dup % 10]) 

                continue

            return true; 

        }

        return false; 

    }

    public static void main(String[] args) 

    { 

        String number = "31462708"; 

          

        int l = number.length(); 

      

        if (solve(number, l)) 

            System.out.println("Yes"); 

        else

            System.out.println("No"); 

    } 
} 
