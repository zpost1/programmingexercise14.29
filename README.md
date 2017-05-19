/*
  Project:programming exercises 14.29
  Name: zelijah post
  Date:10-12-16
  Description:bean machine
*/
package programmingexercise14.pkg29;

import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.stage.Stage;
import javafx.scene.Scene;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.scene.shape.Line;
public class Programmingexercise1429 extends Application {
    
    @Override
    public void start(Stage primaryStage){
        //set stage length
        Circle circle = new Circle();
        circle.setCenterX(820);
        circle.setCenterY(220);
        circle.setRadius(10);
        circle.setStroke(Color.WHITE);
        circle.setFill(Color.WHITE);
        //HOLDERS
        int x = 460;
        int y = 120;
        int k = 0;
        int r = 460;
        int rx = 440;
        int ry = 70;
        int m = 30;
        int m2 = 0;
        Pane pane = new Pane();
        // make lines
        for (int q = 1 ;q<=14;q++){
        Line line1 = new Line(rx,ry,rx+m2,ry+m);
        line1.setStrokeWidth(1);
        line1.setStroke(Color.BLACK);
        rx = rx +m2;
        ry = ry +m;
        if(q==1){
            m2 = -140;
            m = 215;
        }else if(q == 2){
            m2 = 0;
            m = 60;
        }else if(q >= 3 && q <11){
            m2 = 38;
            m = 0;
            if (q == 3){
                Line l = new Line(rx,ry,rx,ry-60);
            l.setStrokeWidth(0);
            l.setStroke(Color.GREY);
            pane.getChildren().add(l);
            }else{
            Line l = new Line(rx,ry,rx,ry-70);
            l.setStrokeWidth(1);
            l.setStroke(Color.BLACK);
            pane.getChildren().add(l);
            }
        }else if(q == 11){
            m2 = 0;
            m = -60;
        }else if(q == 12){
            m2 = -120;
            m = -215;
        }else if(q == 13){
            m2 = 0;
            m = -30;
        }
        
        pane.getChildren().add(line1);
        }
        for (int loo = 1; loo <= 7;loo++){
        k = 0;
        //make line of pegs
        while(k <loo){
        Circle p1 = new Circle();
        p1.setCenterX(x);
        p1.setCenterY(y);
        p1.setRadius(10);
        p1.setStroke(Color.RED);
        p1.setFill(Color.RED);
        pane.getChildren().add(p1);
        k++;
        //spaces pegs
        x = x + 38;
        }
        //starts new line
        y = y+30;
        x = r-20;
        r = x;
        }
        
        pane.getChildren().add(circle);
        
        //creates a scene and place it in the stage
        pane.setPadding(new Insets(5, 5,5, 5));
        Scene scene = new Scene(pane);
        primaryStage.setTitle("Exercise14_29");
        primaryStage.setScene(scene);
        primaryStage.setResizable(false);
        primaryStage.show();
    }
    public static void main(String[] args) {
        Application.launch(args);
    }
    
}
