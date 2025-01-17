# Neighboring-Bitwise-XOR
A 0-indexed array derived with length n is derived by computing the bitwise XOR (⊕) of adjacent values in a binary array original of length n.
class Solution {
    public boolean doesValidArrayExist(int[] derived) {
        int n=derived.length;
        int[] org=new int[n];
        for(int i=1; i<n; i++){
            org[i]=derived[i-1]^org[i-1];
        }
        for(int i=0; i<n; i++){
            int idx=(i+1)%n;
            if(derived[i]!=(org[i]^org[idx])) return false;
        }

        return true;
    }
}
