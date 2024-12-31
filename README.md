# -6Companies30days

problem No.1 Circle and Rectangle Overlapping

You are given a circle represented as (radius, xCenter, yCenter) and an axis-aligned rectangle represented as (x1, y1, x2, y2), where (x1, y1) are the coordinates of the bottom-left corner, and (x2, y2) are the coordinates of the top-right corner of the rectangle.

Return true if the circle and rectangle are overlapped otherwise return false. In other words, check if there is any point (xi, yi) that belongs to the circle and the rectangle at the same time.



CODE
class Solution {
public:
    bool checkOverlap(int radius, int xCenter, int yCenter, int x1, int y1, int x2, int y2) {
        x1 = x1 - xCenter; x2 = x2 - xCenter;
        y1 = y1-yCenter; y2 = y2 - yCenter;
        int minX = x1 * x2 > 0 ? min(x1*x1, x2*x2) : 0,  minY = y1 * y2 > 0 ? min(y1*y1, y2*y2) : 0;
        return minY + minX <= radius * radius;
    }
};
