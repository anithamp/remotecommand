import java.io.*;
import java.net.*;
import java.lang.Runtime;

public class Server
{ 
public static void main(String args[])throws IOException
{
ServerSocket ss=new ServerSocket(8000);
Socket s=ss.accept();
String cmd;
BufferedReader in=new BufferedReader(new InputStreamReader(s.getInputStream()));
PrintWriter out=new PrintWriter(s.getOutputStream(),true);
cmd=in.readLine();
String cmd[]=new String[3];
cmd[0]="/bin/sh";
cmd[1]="-c";
cmd[2]=in.readUTF();
Runtime r= Runtime.getRuntime();
Process p=null;
try
{   
p=r.exec(cmd);
System.out.println("Executing command : "+cmd);

BufferedReader br=new BufferedReader(new InputStreamReader(p.getInputStream()));
String line;
String k="";
while((line=br.readLine())!=null)
{

k=k+line+"\n";

} 

out.println(k);

}
catch(Exception e)
{ 
System.out.println("Error"+e);
}

s.close();
} 
}

 
