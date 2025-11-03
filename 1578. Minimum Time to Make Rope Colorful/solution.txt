class Solution {
    public int minCost(String colors, int[] neededTime) {
        int ans=0;
        char prevC=colors.charAt(0);
        int prevT=neededTime[0];
        for(int i=1;i<neededTime.length;i++){
            char currC=colors.charAt(i);
            int currT=neededTime[i];
            if(prevC==currC){
                if(prevT<currT){
                    ans+=prevT;
                    prevT=currT;
                    prevC=currC;
                }
                else{
                    ans+=currT;
                }
            }
            else{
                prevC=currC;
                prevT=currT;
            }
        }
        return ans;
    }
}