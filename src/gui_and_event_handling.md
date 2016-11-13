## GUI and Event-Handling

In Java GUI, y is the vertical axis and x is the horizontal one.

####``JFrame``
* ``import javax.swing``
* an **object** represents a **window** 
* host all the **Swing component**
* has **windowing icons** for **minimizing, mximizing* and **closing**
* ``JFrame()``: default constructor
* ``setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE)``: make program **quit** when window is closed
* ``add(someWidget)``: add wdiget to the frame
* ``add(someWidget, location)``: add ``someWidget`` into ``location``.$location\in\{BorderLayout.NORTH, BorderLayout.WEST, BorderLayout.CENTER, BorderLayout.EAST, BorderLayout.SOUTH\}$
* ``repaint()``: repaint the frame and therefore ``paintComponent()`` will be called
* ``setSize(width,height)``
* ``setVisible(isVisible)``: set the visibility of ``JFrame`` as ``isVisible`` 

####``Swing``
* the widget of the window
* ``import javax.swing``
* most of the common Swing components extend from ``javax.swing.JComponent``
* we classify components into __interactice__ and __backgroud__ components, however, this distinction is artificial
* we can usually add __interactive__ component into __background__ component
* ``JLabel``:
	* ``label.setText(str)``

####Create a GUI
1. Create a **JFrame**:``JFram frame = new JFrame()``
2. Create some widgets (Swing): ``JButton button = new JButton("click me")``
3. Add the widget to the frame: ``frame.add(button)``
4. Display:
```java
frame.setSize(300,300);
frame.setVisible(true);
```

####Event Handling
* ``import java.awt.event``
* Swing GUI components are **event source** turning **user actions** into **events**
* **Event Classes** represent certain type of events (e.g. ``ActionEvent``,``MouseEvent``) 
	* ``event.getSource()`` return the source of event
* **listener interface**: implement certain **listener interface** to handle certain events (e.g. ``ActionListener``, ``MouseListener``)
	* a **listener interface** may have more than one method 
* **listener**: the class the implement **listener interface**
	* **register**: a **listener** must register itself to **event source** to receive events.
	* **register method**: (e.g. ``addActionListener(someListener)``, ``addMouseListener(someListener)``)
	
####Display User Designed Graphic
* define a **subclass** of **JPanel**
* override ``paintComponent(Graphics g)`` method. However, we will never call this method by ourselves
* **Graphics**:
	* ``g.setColor(Color.CONST)`` set color as ``CONST``
		* ``Color color = new Color(red_c, green_c, blue_c )``, where ``red_c``,``green_c`` and ``blue_c`` are integer constant.
	* ``g.fillRect(x,y,width,height)``
	* ``g.fillOval(x,y,width,height)``
	* ``g.drawImage(image,width, height,this)``
* **Graphics2D**: a subclass of **Graphics**
	* the argument passed in ``paintComponent(Graphics g)`` actuallay references to a **Graphics2D** object so we can cast it
* **Image**:
	* ``Image image = new ImageIcon(file_path).getImage()``
	
####Inner class
* class defined within another class
* can access **all** the methods and instance variables of the **outer class** and vice-versa
* tied to **outer class objects** on the heap
* can't access other **outer class** except the one it is tied to

####Layout Manager
* **BorderLayout**: default layout for a frame with 5 regions. Nort and South Components will get prefered height and as wide as the frame. East and West Components will get prefered width and as high as remain. Center will get the space remained
* **FlowLayout**: default layout for a panel. Components are laid out left to right in the order that they are added. When a component doesn't fit horizontally, it drops to the next "line" in the layout.
* **BoxLayout**: like a ``FlowLayout`` but it can stack components either **vertically** or **horizontally**
	* ``setLayout(new BoxLayout(panel,BoxLayout.Y_AXIS))``
* **GridBagLayout**:
	* Components are placed in a
	* Rows can be of different heights
	* Columns can be of different widths 
	* Components can span multiple rows or columns
	* The size and placement of a component in the grid is specified by a GridBagConstraints object
	* **gridx** x-pos of cell containing leading column
	* **gridy** y-pos of cell containing leading row
	* **gridwidth** num of cells in a row
	* **gridheight** num of cells in a column
	* **weightx** specifies how to distribute extra horizontal space
	* **weighty** specifies how to distribute extra vertical space
```java
	    JFrame frame = new JFrame();
	    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	    
	    JPanel panel = new JPanel(); 
	    panel.setLayout(new GridBagLayout());
	    GridBagConstraints c = new GridBagConstraints();
	    c.gridx = 0;
	    c.gridy = 0;
	    c.gridwidth = 1; // default value
	    c.gridheight = 1; // default value
	    c.weightx = 0.0; // default value
	    c.weighty = 0.0; // default value
	    c.anchor = GridBagConstraints.CENTER; // default value
	    c.fill = GridBagConstraints.HORIZONTAL;
	    c.insets = new Insets(0, 0, 0, 0); // default value
	    c.ipadx = 0; // default value
	    c.ipady = 0; // default value
	    
	    JButton button = new JButton("Button 1");
	    c.weightx = 0.5;
	    panel.add(button, c);
	    
	    button = new JButton("Button 2");
	    c.gridx = 1; // 2nd column
	    panel.add(button, c);
	    
	    button = new JButton("Button 3");
	    c.gridx = 2; // 3rd column
	    panel.add(button, c);
	    
	    button = new JButton("Button 4");
	    c.gridx = 0; // 1st column
	    c.gridy = 1; // 2nd row
	    c.gridwidth = 3; // spans 3 columns
	    c.weightx = 0.0;
	    c.ipady = 40; // makes the button tall
	    panel.add(button, c);
	    
	    button = new JButton("Button 5");
	    c.gridx = 1; // 2nd column
	    c.gridy = 2; // 3rd row
	    c.gridwidth = 2; // spans 2 columns
	    c.weighty = 1.0; // takes up extra vertical space
	    c.anchor = GridBagConstraints.SOUTH;
	    c.insets = new Insets(10, 0, 0, 0); // top padding
	    c.ipady = 0;
	    panel.add(button, c);
	    
	    frame.add(panel);
	    frame.pack();
	    frame.setVisible(true);
```