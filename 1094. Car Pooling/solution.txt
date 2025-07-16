class Solution {
    public boolean carPooling(int[][] trips, int capacity) {
        int diff[]=new int[1001];
        for(int i=0;i<trips.length;i++){
            diff[trips[i][1]]+=trips[i][0];
            diff[trips[i][2]]-=trips[i][0];
        }
        int sum=0;
        for(int i=0;i<1001;i++){
            sum+=diff[i];
            if(sum>capacity){
                return false;
            }
        }
        return true;
    }
}