---
title: 'Lync Server 2013: Instalar los archivos del servidor de mediación'
TOCTitle: Instalar los archivos del servidor de mediación
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48277132
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar los archivos del servidor de mediación en Lync Server 2013

 

_**Última modificación del tema:** 2012-08-06_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.

Siga los pasos de este tema para ejecutar el Asistente para la implementación de Lync Server 2013 e instalar los archivos para el Servidor de mediación en un equipo que haya agregado a un Grupo de servidores de mediación al usar el Generador de topologías para definir y publicar el grupo. Al instalar archivos para el Servidor de mediación también se instala y asigna el certificado que cada equipo necesita en un Grupo de servidores de mediación.

En este sitio, si ha ya implementado Servidores de mediación ubicados en los Grupos de servidores front-end o el Servidor Standard Edition, omita este paso y continúe en [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).


> [!NOTE]
> En este tema se supone que ya se ha definido y publicado un Grupo de servidores de mediación independientes como se describe en <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Definir un servidor de mediación en el Generador de topologías en Lync Server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">Publicar la topología en Lync Server 2013</A> en la documentación sobre implementación, y que se ha comprobado que los equipos en dicho Grupo de servidores de mediación cumpla los requisitos descritos en <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Requisitos previos de software para la telefonía IP empresarial en Lync Server 2013</A> y <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013</A>.



## Para instalar los archivos de un grupo de servidores de mediación independiente

1.  En el medio de instalación, haga clic con el botón secundario en *\<medio de instalación\>* **\\Setup\\amd64\\Setup.exe** y, a continuación, seleccione **Ejecutar como administrador**.

2.  En la página **Ubicación de la instalación**, haga clic en **Aceptar**.

3.  En la página **Contrato de licencia para el usuario final**, seleccione **Acepto** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).

4.  En la página del **Asistente para la implementación de Lync Server 2010**, haga clic en **Instalar o actualizar el sistema Lync Server**.

5.  Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.

6.  En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente del Almacén de administración central**; a continuación, haga clic en **Siguiente**.

7.  En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.

8.  Junto a **Paso 2: Configuración o supresión de componentes de Lync Server**, haga clic en **Ejecutar** y seleccione **Siguiente**.

9.  En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.

10. Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.

11. Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.

12. Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.

13. En el equipo en el que se ejecuta Panel de control de Lync Server, en la página **Topología** de Panel de control de Lync Server compruebe que el estado de servicio del servidor de mediación presente una marca de verificación verde. Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación. En el menú **Acción**, haga clic en **Iniciar todos los servicios**.

Si ha agregado más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del Grupo de servidores de mediación. Si no debe instalar archivos del Servidor de mediación para ningún otro equipo, siga los procedimientos de [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) para configurar los parámetros de la conexión de enlace troncal entre este Grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su homólogo.

## Vea también

#### Conceptos

[Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

