---
title: 'Lync Server 2013: Instalar las herramientas administrativas de Lync Server'
TOCTitle: Instalar las herramientas administrativas de Lync Server
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48275873
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar las herramientas administrativas de Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

En este tema se describe cómo instalar las herramientas administrativas que debe usar para implementar y administrar Lync Server 2013. Las herramientas administrativas se instalan de forma predeterminada en cada servidor en el que se ejecuta Lync Server 2013. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Se recomienda encarecidamente que instale las herramientas administrativas en un equipo que esté en el mismo dominio o bosque que la implementación de Lync Server 2013 que esté creando, porque de esta manera se asegura de que los pasos de preparación de Servicios de dominio de Active Directory ya estén completos, lo que le permite a usted usar las herramientas administrativas en ese equipo más adelante para publicar su topología.

Asegúrese de revisar los requisitos de infraestructura, sistema operativos, software y derechos de administrador antes de instalar o usar las herramientas administrativas de Lync Server 2013. Para obtener información detallada sobre los requisitos de infraestructura, vea [Requisitos de infraestructura de herramientas administrativas de Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obtener información detallada sobre los requisitos de sistema operativo y software para instalar las herramientas administrativas de Lync Server 2013 vea [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Requisitos adicionales de software para Lync Server 2013](lync-server-2013-additional-software-requirements.md) y [Compatibilidad y requisitos para un servidor adicional en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Para obtener información detallada sobre los permisos y derechos de usuario requeridos para instalar y usar las herramientas, vea [Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

> [!IMPORTANT]  
> Si su organización necesita que ubique Internet Information Services (IIS) y todos los servicios web en una unidad que no sea la unidad del sistema, debe cambiar la ruta de acceso a la ubicación de instalación de los archivos de Lync Server en el cuadro de diálogo de instalación. Si instala los archivos de instalación, incluido OCSCore.msi, a esta ruta de acceso, el resto de los archivos de Lync Server 2013 se implementará también en esta unidad.



## Para instalar las herramientas de administración de Lync Server 2013

1.  Inicie sesión como administrador local (requisito mínimo) en el equipo donde desee instalar las herramientas administrativas. Si ha iniciado la sesión como usuario estándar en los sistemas operativos Windows Vista o Windows 7 y está habilitado el control de cuenta de usuarios (UAC), se le pedirá que indique el administrador local o un nombre de usuario equivalente del dominio y una contraseña.

2.  Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \\Setup\\amd64\\Setup.exe.

3.  Si se le pide que instale Microsoft Visual C++ 2008 distribuibles, haga clic en **Sí**.

4.  En la página **Microsoft Lync Server 2013Ubicación de instalación de Microsoft Lync Server 2010** , haga clic en **Aceptar** . Cambie esta ruta de acceso a otra ubicación o unidad si necesita que los archivos se instalen en una ubicación diferente.
    
    > [!IMPORTANT]  
    > Si su organización necesita que ubique Servicios de Internet Information Server (IIS) y todos los Servicios web en una unidad que no sea la unidad del sistema, debe cambiar la ruta de acceso a la ubicación de instalación de los archivos de Lync Server 2013 en el cuadro de diálogo de instalación. Si instala los archivos de instalación, incluido OCSCore.msi, a esta ruta de acceso, el resto de los archivos de Lync Server 2013 se implementará también en esta unidad.
    


5.  En la página **Contrato de licencia para el usuario final** , revise los términos de la licencia, haga clic en **Acepto** y, a continuación, haga clic en **Aceptar** . Este paso es necesario para poder continuar

6.  En la página **Microsoft Lync Server 2013 – Asistente para la implementación**, haga clic en **Instalar herramientas de administrador**.

7.  Cuando finalice la instalación correctamente, haga clic en **Salir** .

## Vea también

#### Tareas

[Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md)  

#### Conceptos

[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)

