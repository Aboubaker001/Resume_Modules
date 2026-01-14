<div dir="rtl" align="right">

# 📝 ورقة الغش - IHM (JavaFX)

> مراجعة سريعة قبل الامتحان

---

## 🔄 هيكل تطبيق JavaFX

```
Application
    └── Stage (النافذة)
            └── Scene (المشهد)
                    └── Root Node (العقدة الجذر)
                            └── Child Nodes (المكونات)
```

---

## 📌 قبل الفرض - نقاط أساسية

### الكود الأساسي

```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import javafx.stage.Stage;

public class App extends Application {
    @Override
    public void start(Stage stage) {
        // المكونات
        Button btn = new Button("اضغط هنا");
        Label lbl = new Label("مرحباً");
        
        // التخطيط
        VBox root = new VBox(10);
        root.getChildren().addAll(lbl, btn);
        
        // المشهد والنافذة
        Scene scene = new Scene(root, 400, 300);
        stage.setTitle("تطبيقي");
        stage.setScene(scene);
        stage.show();
    }
    
    public static void main(String[] args) {
        launch(args);
    }
}
```

### المكونات الأساسية (Controls)

- [ ] **Button**: زر
  ```java
  Button btn = new Button("نص");
  btn.setOnAction(e -> { /* action */ });
  ```

- [ ] **Label**: نص ثابت
  ```java
  Label lbl = new Label("نص");
  ```

- [ ] **TextField**: حقل نص
  ```java
  TextField tf = new TextField();
  String text = tf.getText();
  ```

- [ ] **TextArea**: منطقة نص متعددة الأسطر
  ```java
  TextArea ta = new TextArea();
  ```

- [ ] **CheckBox**: مربع اختيار
  ```java
  CheckBox cb = new CheckBox("خيار");
  boolean selected = cb.isSelected();
  ```

- [ ] **RadioButton**: زر راديو
  ```java
  ToggleGroup group = new ToggleGroup();
  RadioButton rb1 = new RadioButton("خيار 1");
  rb1.setToggleGroup(group);
  ```

- [ ] **ComboBox**: قائمة منسدلة
  ```java
  ComboBox<String> cb = new ComboBox<>();
  cb.getItems().addAll("أ", "ب", "ج");
  ```

### التخطيطات (Layouts)

- [ ] **VBox**: ترتيب عمودي
  ```java
  VBox vbox = new VBox(10); // spacing = 10
  vbox.getChildren().addAll(node1, node2);
  ```

- [ ] **HBox**: ترتيب أفقي
  ```java
  HBox hbox = new HBox(10);
  ```

- [ ] **GridPane**: شبكة
  ```java
  GridPane grid = new GridPane();
  grid.add(node, col, row);
  ```

- [ ] **BorderPane**: خمس مناطق
  ```java
  BorderPane bp = new BorderPane();
  bp.setTop(node);
  bp.setCenter(node);
  bp.setBottom(node);
  bp.setLeft(node);
  bp.setRight(node);
  ```

- [ ] **StackPane**: تكديس
  ```java
  StackPane sp = new StackPane();
  ```

### معالجة الأحداث

- [ ] **طريقة Lambda** (الأفضل):
  ```java
  btn.setOnAction(e -> {
      System.out.println("تم الضغط!");
  });
  ```

- [ ] **طريقة Anonymous Class**:
  ```java
  btn.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
          System.out.println("تم الضغط!");
      }
  });
  ```

### FXML

- [ ] **ملف FXML**:
  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <?import javafx.scene.layout.*?>
  <?import javafx.scene.control.*?>
  
  <VBox fx:controller="Controller">
      <Button fx:id="btn" text="اضغط" onAction="#handleClick"/>
  </VBox>
  ```

- [ ] **Controller**:
  ```java
  public class Controller {
      @FXML private Button btn;
      
      @FXML
      private void handleClick(ActionEvent e) {
          // المنطق
      }
  }
  ```

- [ ] **تحميل FXML**:
  ```java
  Parent root = FXMLLoader.load(getClass().getResource("view.fxml"));
  ```

---

## 📐 CSS في JavaFX

```java
// تطبيق ملف CSS
scene.getStylesheets().add("style.css");

// تطبيق style مباشر
btn.setStyle("-fx-background-color: blue; -fx-text-fill: white;");
```

---

## ⚠️ أخطاء شائعة

| الخطأ | التصحيح |
|:------|:--------|
| نسيان `launch(args)` | يجب استدعاؤها في `main` |
| عدم إضافة المكونات للـ Parent | استخدم `getChildren().add()` |
| خلط بين Scene و Stage | Stage = النافذة، Scene = المحتوى |

---

## 🔗 روابط سريعة

- [📘 فهرس المقياس](README.md)
- [📖 قاموس المصطلحات](glossary.md)
- [⬆️ فهرس السداسي](../00_Index.md)

</div>
