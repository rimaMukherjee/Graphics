import java.awt.*;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;
public class Flag1
{
    public static void main(String s[])
    {
        newframe m=new newframe();
        m.setSize(600,600); //width,height
        m.setVisible(true);;
    }
}
class newframe extends Frame {
    public newframe() {
        addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                dispose();
            }
        });
    }

    public void paint(Graphics g) {

        g.setColor(Color.white);
        g.fillRect(50, 50, 300, 200);

        g.setColor(Color.green);
        g.fillRect(50, 150, 300, 50);

        g.setColor(Color.orange);
        g.fillRect(50, 50, 300, 50);

        g.setColor(Color.blue);
        g.fillOval(160, 97, 56, 56);

        g.setColor(Color.white);
         drawSpokes(g,188,124,24,27);
    }

    private void drawSpokes(Graphics g, int centerX, int centerY, int numSpokes, int spokeLength) {
        double angle = 0;
        double angleIncrement = 2 * Math.PI / numSpokes;
        for (int i = 0; i < numSpokes; i++) {
            int endX = (int) (centerX + spokeLength * Math.cos(angle));
            int endY = (int) (centerY + spokeLength * Math.sin(angle));
            g.drawLine(centerX, centerY, endX, endY);
            angle += angleIncrement;
        }
    }
}
