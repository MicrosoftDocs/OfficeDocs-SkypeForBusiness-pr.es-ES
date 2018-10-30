---
title: "Lync Server 2013: Configurar nombres de dominio completos de granja de servidores web"
TOCTitle: Configurar los nombres de dominio completos (FQDN) de la granja de servidores web
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48276687
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar los nombres de dominio completos (FQDN) de la granja de servidores web para Lync Server 2013

 

_**Última modificación del tema:** 2013-03-29_

Al definir la configuración del servidor Standard Edition, el Grupo de servidores front-end y el Director o Grupo de directores en Generador de topologías, se configura un nombre de dominio completo (FQDN) de servicios web externos. Durante el proceso de inicio de sesión de un cliente hospedado en el servidor Standard Edition o en el Grupo de servidores front-end, los FQDN de servicios web configurados se envían mediante el aprovisionamiento dentro de banda. Si necesita agregar o cambiar la URL de los servicios web externos, use Generador de topologías para configurar o volver a configurar la configuración de servicios web mediante el procedimiento que se indica en este tema.

## Para configurar el FQDN de un grupo de servidores externo para servicios web

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En Generador de topologías, en el árbol de consola bajo **Servidores front-end Standard Edition** , **Servidores back-end Enterprise Edition** y **Directores** , haga clic con el botón secundario en el nombre del grupo de servidores que debe editar y, a continuación haga clic en **Editar propiedades** .

3.  En la sección **Servicios web** , agregue o edite el **FQDN de servicios web externos** .

4.  Revise y ajuste los **Puertos de escucha** para HTTP y HTTPS. Los valores predeterminados serán:
    
      - **Puertos de escucha:** HTTP 8080, HTTPS 4443
    
      - **Puertos de escucha:** HTTP 80, HTTPS 443
    
    Donde los **Puertos de escucha** son los puertos que los servicios web externos configurarán para recibir solicitudes desde el proxy inverso y los **Puertos publicados** son los puertos que publica externamente el proxy inverso y se comunican a los clientes durante el aprovisionamiento en banda.

5.  Cuando haya completado las adiciones y actualizaciones, haga clic en **Aceptar** para continuar.

6.  Haga clic con el botón derecho en **Lync Server 2013** y, a continuación, haga clic en **Publicar**.
    
    > [!IMPORTANT]  
    > Una vez finalizada la publicación correctamente, puede aparecer un vínculo que le informa de que hay pasos adicionales que deban llevarse a cabo. Si hace clic en el vínculo, se abre una lista de servidores afectados por los cambios realizados en Generador de topologías que le pide que vuelva a ejecutar la Asistente para la implementación de Lync Server en cada servidor enumerado para actualizar la configuración de componentes agregados, quitados o modificados.
    


7.  Repita estos pasos para todos los servidores Standard Edition, los Grupo de servidores front-end y los Director o Grupo de directores de la organización.

