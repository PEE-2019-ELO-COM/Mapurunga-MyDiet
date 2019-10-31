# Mapurunga-VSS-SDK-COM

Programa que faz a comunicação entre o simulador VSS-SDK e o código da equipe de VSS da roboime. Consiste em 2 partes, uma em C++ e outra em LabView, a primeira rodando em ubuntu e outra em windows, ambas fazendo recebimento e envio de pacotes. Sendo a parte em C++ trabalhando em TCP e a LabView em UDP, com o programa fazendo o link entre as duas. Os pacotes serão enviados via protobufs da google.

## Biblioteca gráfica

Será utilizado a interface gráfica dafault do LabView (Front Panel)

## Pacotes

Os pacotes serão da seguinte forma, podendo ser alterados de acordo com demanda do projeto:

package Viewer;

message DataFriend {
	required float ballPoseX = 1;
	required float ballPoseY = 2;
	required float friend1PoseX = 3;
	required float friend1PoseY = 4;
	required float friend1Yaw = 5;
	required float friend2PoseX = 6;
	required float friend2PoseY = 7;
	required float friend2Yaw = 8;
	required float friend3PoseX = 9;
	required float friend3PoseY = 10;
	required float friend3Yaw = 11;
}

message DataEnemy{
	required float enemy1PoseX = 1;
	required float enemy1PoseY = 2;
	required float enemy2PoseX = 3;
	required float enemy2PoseY = 4;
	required float enemy3PoseX = 5;
	required float enemy3PoseY = 6;
}

message DataReceiver{
	required uint32 friend0VelDir = 1;
	required uint32 friend1VelDir = 2;
	required uint32 friend2VelDir = 3;
	required uint32 friend0VelEsq = 4;
	required uint32 friend1VelEsq = 5;
	required uint32 friend2VelEsq = 6;
}
