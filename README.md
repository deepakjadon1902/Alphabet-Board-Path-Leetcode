class Solution {
    public String alphabetBoardPath(String target) {
        // Where You start From
        // Current Position
        int n = 0;
        int m = 0;

        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < target.length(); i++) {
            char ch = target.charAt(i);

            int n1 = (ch - 'a') / 5;
            int m1 = (ch - 'a') % 5;
            // if you want to move UpSide form the Current Position..
            while (n1 < n) {
                n--;
                sb.append('U');
            }
            // if you want to move Right form the Current Position..
            while (m1 > m) {
                m++;
                sb.append('R');
            }
            // if you want to move Left form the Current Position..
            while (m1 < m) {
                m--;
                sb.append('L');
            }
            // if you want to move Down form the Current Position..
            while (n1 > n) {
                n++;
                sb.append('D');
            }
            sb.append('!');
        }
        return sb.toString();
    }
}
