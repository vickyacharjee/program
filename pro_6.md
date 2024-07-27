# JAVA
```
package com.example.all_views;
import android.app.Dialog;
import android.content.Context;
import android.content.DialogInterface;
import android.os.Bundle;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.RadioButton;
import android.widget.RadioGroup;
import android.widget.Spinner;
import android.widget.Toast;
import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;
public class MainActivity extends AppCompatActivity {
Button sub;
@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
EdgeToEdge.enable(this);
setContentView(R.layout.activity_main);
Button sub=findViewById(R.id.submit);
sub.setOnClickListener(new View.OnClickListener() {
@Override
public void onClick(View v) {
showMessage(MainActivity.this,"User Information","Successfully
completed");
}
});
String[] item=new String[]{"India", "Pakisthan", "China", "America",
"England"};
ArrayAdapter adapter = new ArrayAdapter<>(this,
android.R.layout.simple_spinner_item, item);
adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_i
tem);
Spinner spinner = findViewById(R.id.country);
spinner.setAdapter(adapter);
}
public void showMessage(Context con,String t, String msg)
{
AlertDialog.Builder builder = new AlertDialog.Builder(con);
builder.setTitle(t);
builder.setMessage(msg);
builder.setPositiveButton("OK", new DialogInterface.OnClickListener() {
@Override
public void onClick(DialogInterface dialog, int which) {
dialog.dismiss();
}
});
builder.show();
}
}
```

# XML
```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android">
<gradient android:startColor="#64EFAE"
android:endColor="#84FFFF"
android:angle="120"
android:gradientRadius="5dp"/>
<corners android:radius="20dp"/>
</shape>
c. Create another background resource for inner layout. Set filename as
bg_inner.xml, root element as shape and then click ok. Modify the
bg_inner.xml file
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android">
<gradient android:startColor="#64F194"
android:endColor="#B242C5"
android:angle="120"
android:gradientRadius="5dp"/>
<corners android:radius="20dp"
android:topLeftRadius="70dp"
android:bottomRightRadius="70dp"/>
</shape>
d. Likewise, create another background resource for view. Set filename as bg.xml,
root element as shape and then click ok. Modify the bg..xml file
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android">
<solid android:color="#2860F367"/>
<corners android:radius="30dp" />
<stroke android:color="#00BFA5"
android:width="2dp"/>
</shape>
5. Create a TextView, EditText, ToggleButton, ImageView, RadioGroup,
RadioButton, spinner and a Button resource in activity_main.xml and update the
following code.
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:id="@+id/main"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity"
android:gravity="center"
android:orientation="vertical"
android:padding="30dp"
android:background="@drawable/bg_outer">
<TextView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="User Information"
android:textSize="30sp"
android:textStyle="bold"
android:textColor="#26389C"/>
<ImageView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:src="@drawable/account_img"/>
<ToggleButton
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:textOn="Active"
android:textOff="Inactive"/>
<View
android:layout_width="match_parent"
android:layout_height="40dp"/>
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:paddingTop="30dp"
android:paddingBottom="30dp"
android:paddingLeft="5dp"
android:paddingRight="5dp"
android:orientation="vertical"
android:background="@drawable/bg_inner">
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:padding="5dp">
<TextView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Name"
android:textSize="20sp"
android:textStyle="bold"
android:textColor="#26389C"
android:padding="15dp"/>
<EditText
android:layout_width="match_parent"
android:layout_height="60dp"
android:id="@+id/name"
android:background="@drawable/bg"
android:padding="15dp"/>
</LinearLayout>
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:padding="5dp">
<TextView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="E-mail"
android:textSize="20sp"
android:textStyle="bold"
android:textColor="#26389C"
android:padding="15dp"/>
<EditText
android:id="@+id/email"
android:layout_width="match_parent"
android:layout_height="60dp"
android:ems="10"
android:inputType="textEmailAddress"
android:background="@drawable/bg"
android:padding="15dp"/>
</LinearLayout>
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:padding="5dp">
<TextView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Sex"
android:textSize="20sp"
android:textStyle="bold"
android:textColor="#26389C"
android:padding="15dp"
android:paddingEnd="40dp"
/>
<RadioGroup
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:background="@drawable/bg"
android:orientation="horizontal"
android:id="@+id/sex">
<RadioButton
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:id="@+id/male"
android:padding="15dp"
android:text="Male"
android:textColor="#26389C"
android:textSize="20sp"
android:textStyle="bold" />
<RadioButton
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:id="@+id/female"
android:padding="15dp"
android:text="Female"
android:textColor="#26389C"
android:textSize="20sp"
android:textStyle="bold" />
</RadioGroup>
</LinearLayout>
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:padding="5dp">
<TextView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Country"
android:textSize="20sp"
android:textStyle="bold"
android:textColor="#26389C"
android:padding="15dp"
android:paddingEnd="5dp" />
<Spinner
android:layout_width="match_parent"
android:layout_height="60dp"
android:id="@+id/country"
android:padding="15dp"
android:background="@drawable/bg"/>
</LinearLayout>
</LinearLayout>
<View
android:layout_width="match_parent"
android:layout_height="40dp"/>
<Button
android:layout_width="210dp"
android:layout_height="wrap_content"
android:id="@+id/submit"
android:background="@drawable/bg"
android:padding="15dp"
android:text="Submit"
android:textColor="#26389C"
android:textSize="20sp"
android:textStyle="bold" />
</LinearLayout>
```