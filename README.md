GroupLayoutPane
---------------

Replacement for Swing's [GroupLayout](http://docs.oracle.com/javase/8/docs/api/javax/swing/GroupLayout.html) in JavaFX. Requires Java 8.

Usage example:

```java
GroupLayoutPane root = new GroupLayoutPane();
root.setPadding(new Insets(5));
StackPane n1 = new StackPane();
n1.setStyle("-fx-background-color: red");
StackPane n2 = new StackPane();
n2.setStyle("-fx-background-color: green");
StackPane n3 = new StackPane();
n3.setStyle("-fx-background-color: blue");

root.getChildren().add(n1);
root.getChildren().add(n2);
root.getChildren().add(n3);

root.setHorizontalGroup(root.createParallelGroup()
                        .addGroup(root.createSequentialGroup()
                                  .addNode(n1, 10, 100, 200)
                                  .addNode(n2, 10, 100, 200))
                        .addNode(n3, 20, 300, 400));
root.setVerticalGroup(root.createSequentialGroup()
                      .addGroup(root.createParallelGroup()
                                .addNode(n1, 10, 100, 200)
                                .addNode(n2, 10, 100, 200))
                      .addNode(n3, 20, 200, 400));

Scene scene = new Scene(root);
stage.setScene(scene);
stage.show();
```
