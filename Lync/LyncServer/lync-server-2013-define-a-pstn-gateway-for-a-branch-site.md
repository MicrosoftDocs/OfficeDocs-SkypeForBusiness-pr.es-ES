---
title: 'Lync Server 2013: Definir una puerta de enlace RTC para un sitio de sucursal'
TOCTitle: Definir una puerta de enlace RTC para un sitio de sucursal
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48275921
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Realice este procedimiento en el sitio central, que contiene por lo menos un Grupo de servidores front-end o Servidor Standard Edition.

> [!IMPORTANT]  
> Antes de llevar a cabo el procedimiento, se deben cumplir las siguientes condiciones:
> <ul>
> <li><p>Lync Server 2013  software de comunicaciones debe estar instalado en el sitio central.</p></li>
> <li><p>Servidor de mediación debe estar implementado en el sitio central.</p></li>
> </ul>


## Para definir una puerta de enlace RTC

1.  Haga clic sucesivamente en **Inicio** , **Todos los programas** , **Microsoft Lync Server** y **Generador de topologías de Lync Server** .

2.  En el árbol de consola, expanda el sitio central, expanda **Sucursales** , expanda el nombre de la sucursal para la que desee definir una puerta de enlace de la red telefónica conmutada (RTC) y, a continuación, expanda **Componentes compartidos** .

3.  Haga clic con el botón secundario en **Puertas de enlace RTC** y, a continuación, haga clic en **Nueva puerta de enlace IP/RTC** .

4.  En el cuadro de diálogo **Definir la nueva puerta de enlace RTC/IP** , haga clic en **Dirección IP o FQDN de la puerta de enlace** y, a continuación, escriba el nombre de dominio completo (FQDN) o la dirección IP de la puerta de enlace que está implementando en la sucursal.

5.  Haga clic en **Puerto de escucha de la puerta de enlace RTC/IP** y acepte los valores predeterminados.

6.  En la lista **Protocolo de transporte SIP** , haga clic en el protocolo de transporte que usa la puerta de enlace y, a continuación, haga clic en **Aceptar** .
    

    > [!NOTE]
    > Por motivos de seguridad, se recomienda encarecidamente usar una puerta de enlace RTC compatible con Seguridad de la capa de transporte (TLS).



> [!TIP]  
> Use el cmdlet Set- <strong>Set-CsPstnGateway</strong> para modificar las propiedades de una puerta de enlace RTC. Para ver más detalles, consulte <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</a> en la Ayuda del Shell de administración de Lync Server.



**Paso siguiente** para la resistencia de sucursales: [Configuración de usuarios para la resistencia del sitio de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

## Vea también

#### Conceptos

[Opciones de implementación de la puerta de enlace RTC en Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)

