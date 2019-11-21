# Mapurunga-VSS-SDK-COM

Programa que faz a comunicação entre o simulador VSS-SDK e o código da equipe de VSS da roboime. Consiste em 2 partes, uma em C++ e outra em LabView, a primeira rodando em ubuntu e outra em windows, ambas fazendo recebimento e envio de pacotes. Sendo a parte em C++ trabalhando em TCP e a LabView em UDP, com o programa fazendo o link entre as duas. Os pacotes serão enviados via protobufs da google. Os código desenvolvidos até o momento podem ser encontrado nas branches [vss-sample](https://github.com/roboime/VSS/tree/vss-sample) e [vss-simulator](https://github.com/roboime/VSS/tree/vss-simulator) do repositório da equipe da VSS da roboime.

LabView:
![](/img/img3.PNG)

Xming no Ubuntu usando QT:
![](/img/img2.PNG)

Vídeo dos projetos comunicando:
http://redmine.roboime.com.br/attachments/download/4870/video1.mp4

## Fluxograma
![](/img/img6.PNG)

## Requisitos
*Labview 2018+,
*Subsistema do windows para linux,
*[VSS-SDK](https://vss-sdk.github.io/book/general.html) no linux,
*Codigo fonte da equipe VSS da roboime,
*Xming.

## Biblioteca gráfica

Será utilizado a interface gráfica dafault do LabView (Front Panel)

Esboço:

![](/img/img5.png)

Versão atual:

![](/img/img4.PNG)

## Pacotes

Os pacotes serão da seguinte forma, podendo ser alterados de acordo com demanda do projeto:

	syntax = "proto2";

	package RoboimeData;

	message DataYellow {
		required float ballPoseX = 1;
		required float ballPoseY = 2;
		required float yellow0PoseX = 3;
		required float yellow0PoseY = 4;
		required float yellow0Angle = 5;	
		required float yellow1PoseX = 6;
		required float yellow1PoseY = 7;
		required float yellow1Angle = 8;	
		required float yellow2PoseX = 9;
		required float yellow2PoseY = 10;
		required float yellow2Angle = 11;	
		/*required float ballSpeedX = 12;
		required float ballSpeedY = 12;
		required float yellow0SpeedX = 14;
		required float yellow0SpeedY = 15;
		required float yellow0SpeedAngle = 16;
		required float yellow1SpeedX = 17;
		required float yellow1SpeedY = 18;
		required float yellow1SpeedAngle = 19;
		required float yellow2SpeedX = 20;
		required float yellow2SpeedY = 21;
		required float yellow2SpeedAngle = 22;*/
	}
	
	message DataBlue{
		required float blue0PoseX = 1;
		required float blue0PoseY = 2;
		required float blue0Angle = 3;	
		required float blue1PoseX = 4;
		required float blue1PoseY = 5;
		required float blue1Angle = 6;	
		required float blue2PoseX = 7;
		required float blue2PoseY = 8;
		required float blue2Angle = 9;
		/*required float blue0SpeedX = 10;
		required float blue0SpeedY = 11;
		required float blue0SpeedAngle = 12;
		required float blue1SpeedX = 13;
		required float blue1SpeedY = 14;
		required float blue1SpeedAngle = 15;
		required float blue2SpeedX = 16;
		required float blue2SpeedY = 17;
		required float blue2SpeedAngle = 18;*/
	}

	message DataReceiver{
		required uint32 friend0VelEsq = 1;	
		required uint32 friend0VelDir = 2;
		required uint32 friend1VelEsq = 3;	
		required uint32 friend1VelDir = 4;
		required uint32 friend2VelEsq = 5;	
		required uint32 friend2VelDir = 6;
	}	
