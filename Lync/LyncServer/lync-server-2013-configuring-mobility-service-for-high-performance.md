---
title: Configurar el servicio de movilidad para alto rendimiento
TOCTitle: Configurar el servicio de movilidad para alto rendimiento
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48276590
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el servicio de movilidad para alto rendimiento

 

_**Última modificación del tema:** 2013-02-17_

Al instalar el servicio de movilidad de Lync Server 2013 en Servicios de Internet Information Server (IIS) 7.5, el instalador del servicio de movilidad configura algunos parámetros de rendimiento en el Servidor front-end. Se recomienda usar IIS 7.5 para la movilidad. Si usa IIS 7.0 en Windows Server 2008, debe configurar estos parámetros manualmente. Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.

Los parámetros de rendimiento son los siguientes:

  - **maxConcurrentThreadsPerCPU** está configurado en cero (0).

  - **maxConcurrentRequestsPerCPU** está configurado en cero (0).

  - El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).

  - El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).

Si usa IIS 7.0, se recomienda instalar la actualización disponible del artículo 2290617 de Microsoft Knowledge Base, "REVISIÓN: Una revisión está disponible para habilitar la configuración de algunos controles de ASP.NET para cada grupo de aplicaciones en IIS 7.0," en [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0xc0a) para que pueda aplicar los cambios solamente al servicio de movilidad sin influir en otros servicios web.

El siguiente procedimiento describe cómo cambiar los máximos de solicitudes simultáneas y subprocesos de ASP.NET en IIS 7.0 si no instala la actualización disponible en el artículo 2290617 de Knowledge Base. Sin embargo, aunque instale el artículo 2290617 de Knowledge Base, debe usar la documentación proporcionada por el artículo para aplicar los mismos cambios solo para los grupos de aplicaciones IIS internas y externas de movilidad. En este caso, debe usar un archivo de configuración independiente para los parámetros de ASP.NET.

> [!IMPORTANT]  
> Si usa el siguiente procedimiento para cambiar los máximos, los cambios afectarán a los grupos de aplicaciones IIS.



Para más información sobre estos parámetros, vea [http://go.microsoft.com/fwlink/?linkid=234537\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=234537%26clcid=0xc0a).

## Para cambiar los máximos de solicitudes simultáneas y subprocesos

1.  Haga clic en **Iniciar** y, a continuación, en **Ejecutar**.

2.  En el cuadro **Ejecutar**, escriba lo siguiente:
    
        notepad %SystemRoot%\Microsoft.NET\Framework64\v2.0.50727\Aspnet.config

3.  Haga clic en **Aceptar**.

4.  Agregue o reemplace el siguiente elemento \<system.web\> como secundario del elemento \<configuration\> en el archivo Aspnet.:
    
        <system.web>
        <applicationPool maxConcurrentRequestsPerCPU="<#>" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>
        </system.web>
    
    donde \# es 0 para quitar el límite o el nuevo número según se describe anteriormente en esta sección.

5.  Guarde el archivo Aspnet.config y cierre el Bloc de notas.

