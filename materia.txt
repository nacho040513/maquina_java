package maquina_de_estados;
import java.util.Scanner;
public class materia {
	private enum estados{SOLIDO,GAS,LIQUIDO, PLASMA};
	private estados estadoActual = estados.SOLIDO;
	
	public void cambioEstados() {
		Scanner teclado=new Scanner(System.in);
		int temp;
		System.out.println();
		System.out.println("Ingrese la temperatura en grados Celsius");
		temp=teclado.nextInt();
		
	if(estadoActual==estados.LIQUIDO && temp >=100) {
		vaporizacion();
		cambioEstados();
	}else if(estadoActual==estados.LIQUIDO && temp <=0) {
		solidificacion();
		cambioEstados();
	}else if(estadoActual==estados.SOLIDO && temp >=100) {
		sublimacion();
		cambioEstados();
		 cambioEstados();
	}else if(estadoActual==estados.SOLIDO && temp>=-4 && temp <=100) {
		fusion();
		cambioEstados();
	}else if(estadoActual==estados.GAS && temp >=1050) {
		ionizacion();
		cambioEstados();
	}else if(estadoActual==estados.GAS && temp <=0) {
		condensacion();
		cambioEstados();
	}else if(estadoActual==estados.GAS && temp >=600 && temp <= 1050) {
		deposicion();
		cambioEstados();
	}else if(estadoActual==estados.PLASMA && temp >=100 && temp <600) {
		desionizacion();
		cambioEstados();
	}
		
		
	}
	protected void vaporizacion(){
		estadoActual= estados.GAS;
		System.out.print("Evaporado. Estado actual es: "+estadoActual);
		
	}
	protected void condensacion(){
		estadoActual= estados.LIQUIDO;
		System.out.print("Condesado. Estado actual es: "+estadoActual);
		
	}
	protected void solidificacion(){
		estadoActual= estados.SOLIDO;
		System.out.print("Solidificado. Estado actual es:"+estadoActual);
		
	}
	protected void fusion(){
		estadoActual= estados.LIQUIDO;
		System.out.print("Fusionado. Estado actual es: "+estadoActual);
		
	}
	protected void deposicion(){
		estadoActual= estados.SOLIDO;
		System.out.print("Deposicionado. Estado actual es: "+estadoActual);
		
	}
	protected void sublimacion(){
		estadoActual= estados.GAS;
		System.out.print("Sublimado. Estado actual es: "+estadoActual);
		
		
	}
	protected void desionizacion(){
		estadoActual= estados.GAS;
		System.out.print("Desioinizado. Estado actual es: "+estadoActual);
		
	}
	protected void ionizacion(){
		estadoActual= estados.PLASMA;
		System.out.print("Ionizado. Estado actual es: "+estadoActual);
		
	}
	
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		materia materia = new materia();
		materia.cambioEstados();
		
	}

}
