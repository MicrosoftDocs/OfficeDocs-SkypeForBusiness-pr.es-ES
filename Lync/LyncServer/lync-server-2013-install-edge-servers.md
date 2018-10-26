---
title: 'Lync Server 2013: Instalar servidores perimetrales'
TOCTitle: Instalar servidores perimetrales
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48274542
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar servidores perimetrales para Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Lync Server 2013 se instala en los servidores perimetrales a través de la Asistente para la implementación de Lync Server. Cuando se ejecuta el Asistente para la implementación en cada servidor perimetral, se puede llevar a cabo la mayor parte de las tareas necesarias para configurar el servidor en cuestión. Para poder implementar Lync Server 2013 en un servidor perimetral, ya debe haber ejecutado Generador de topologías para definir y publicar la topología del servidor perimetral y, asimismo, haber exportado dicha topología a un medio accesible desde el servidor perimetral. Para obtener información detallada, vea [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) y [Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Una vez que ha usado el Asistente para la implementación para instalar cada uno de los servidores perimetrales, ha instalado y asignado los certificados necesarios y ha iniciado los servicios pertinentes, puede finalizar la instalación haciendo uso de la información contenida en [Configurar la compatibilidad para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md), que le permitirá habilitar y configurar el acceso de usuarios externos, así como la información de [Comprobación de la implementación perimetral en Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md), con la que podrá validar la instalación, incluida la conectividad de servidor y cliente.

## Para instalar un servidor perimetral

1.  Inicie sesión en el equipo en el que desea instalar el servidor perimetral como miembro del grupo Administradores o con una cuenta que tenga derechos o permisos de usuario similares.

2.  Asegúrese de que el archivo de configuración de la topología que creó mediante Generador de topologías (y que, posteriormente, exportó y copió a un medio externo) está disponible en el servidor perimetral; por ejemplo, en el servidor perimetral, conecte la unidad USB en la que ha copiado el archivo de configuración de la topología, o bien confirme el acceso al recurso de red compartido en el que copió dicho archivo.

3.  Inicie el Asistente para la implementación.
    

    > [!NOTE]
    > Si recibe un mensaje en el que se indica que es necesario instalar Microsoft Visual C++ Redistributable, haga clic en <STRONG>Sí</STRONG>. En el siguiente cuadro de diálogo, puede aceptar la <STRONG>Ubicación de instalación</STRONG> predeterminada o bien hacer clic en <STRONG>Examinar</STRONG> para seleccionar otra. Tras ello, haga clic en <STRONG>Instalar</STRONG>. En el siguiente cuadro de diálogo, active la casilla <STRONG>Acepto los términos del contrato de licencia</STRONG> y haga clic en <STRONG>Aceptar</STRONG>.



4.  En el Asistente para la implementación, haga clic en **Instalar o actualizar sistema Lync Server**.

5.  Una vez que el asistente ha averiguado el estado de la implementación, en **Paso 1. Instalar almacén de configuración local**, haga clic en **Ejecutar** y realice lo siguiente:
    
      - En el cuadro de diálogo **Configurar réplica local del almacén de administración central**, haga clic en **Importar desde un archivo (recomendado en servidores perimetrales)**, vaya a la ubicación del archivo de configuración de la topología exportado, seleccione el archivo .zip, haga clic en **Abrir** y, a continuación, en **Siguiente**.
    
      - El Asistente para la implementación lee la información de configuración de este archivo y escribe el archivo de configuración XML en el equipo local.
    
      - Cuando el proceso **Ejecución de comandos** se complete, haga clic en **Finalizar**.

6.  En el Asistente para la implementación, haga clic en **Paso 2: Instalar o eliminar componentes de Lync Server** para instalar los componentes perimetrales de Lync Server 2013 especificados en el archivo de configuración XML almacenado en el equipo local.

7.  Tras completar la instalación, use la información incluida en [Configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar y asignar los certificados necesarios antes de iniciar los servicios.

