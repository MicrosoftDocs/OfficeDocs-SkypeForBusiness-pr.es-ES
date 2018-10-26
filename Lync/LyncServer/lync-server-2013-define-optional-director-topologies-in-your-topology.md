---
title: "Lync Server 2013 : Déf. des topo. facult. de directeur dans votre topologie"
TOCTitle: Definir topologías de Director opcionales en la topología
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48275984
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir topologías de Director opcionales en la topología para Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Los directores de Lync Server 2013 pueden ser servidores de una sola instancia o pueden instalarse como un grupo de servidores de varios directores de carga equilibrada, para aumentar la disponibilidad y la capacidad. Tanto el equilibrio de carga de hardware como el equilibrio de carga del Sistema de nombres de dominio (DNS) son compatibles. Este tema explica cómo configurar el equilibrio de carga DNS en los grupos de servidores de director.

Para publicar, habilitar o deshabilitar una topología correctamente al agregar o quitar un rol de servidor, debe haber iniciado sesión con un usuario que sea miembro de los grupos **RTCUniversalServerAdmins** y **Administradores de dominio** . También puede delegar los permisos y derechos de administrador correspondientes para agregar roles de servidor. Para ver más detalles, vea [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación del servidor Standard Edition o Enterprise Edition. Para realizar otros cambios en la configuración, solo se necesita ser miembro del grupo **RTCUniversalServerAdmins** .

En este tema se describen los pasos para definir y publicar la topología de las dos topologías de Directortopologías:

  - Para definir el Director (instancia única)

  - Para definir el Director (grupo de directores de múltiples)

## Para definir el Director (instancia única)

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En la página de bienvenida, haga clic en **Descargar topología de la implementación existente** .

3.  En el cuadro de diálogo **Guardar topología como** , escriba el nombre y la ubicación de la copia local de la topología existente y, a continuación, haga clic en **Guardar** .

4.  Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director** .

5.  En el cuadro de diálogo **Definir el FQDN del grupo director** , haga lo siguiente:
    
      - En **FQDN del grupo de servidores** , escriba el FQDN del grupo de servidores de director.
    
      - Haga clic en **Grupo de servidores de un solo equipo** y, a continuación, haga clic en **Siguiente** .

6.  En el cuadro de diálogo para **definir el recurso compartido de archivos** cuadro de diálogo, realice una de las siguientes opciones:
    
    1.  Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente** , seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente** .
    
    2.  Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos** , escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos** , escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente** .
    
    > [!IMPORTANT]  
    > El recurso compartido de archivo que especifique o cree en este paso debe existir o crearse antes de publicar la topología.<br />
    > El recurso compartido de archivos asignado a un Director no se utiliza realmente, por lo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.


7.  En el cuadro de diálogo para **especificar la dirección URL de servicios Web** , en la **dirección URL base externa** , especifique el nombre completo para los directores y, a continuación, haga clic en **Finalizar** .
    
    > [!IMPORTANT]  
    > El nombre debe poder resolverse desde los servidores DNS de Internet, y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS a esa URL y las redirige al directorio virtual de servicios web externos de ese director.
    
    
    > [!WARNING]  
    > Si tiene más de un Grupo de servidores front-end o Servidor front-end los servicios Web externos FQDN deben ser únicos. Por ejemplo, si define los servicios Web externos FQDN de un Servidor front-end como <strong>pool01.contoso.com</strong> no puede usar <strong>pool01.contoso.com</strong> para otro Grupo de servidores front-end o Servidor front-end. Si también está implementando Directores, los servicios Web externos FQDN definidos para un Director o Grupo de directores deben ser diferentes de otro Director o Grupo de directores al igual que cualquier Grupo de servidores front-end o Servidor front-end. Si decide omitir los servicios Web externos con un FQDN autodefinido, todos los FQDN deben ser diferentes de otros Grupo de servidores front-end, Director o Grupo de directores.
    


8.  Publique la topología.

## Para definir el Director (grupo de directores de múltiples)

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En la página de bienvenida, haga clic en **Descargar topología de la implementación existente** .

3.  En el cuadro de diálogo **Guardar topología como** , escriba el nombre y la ubicación de la copia local de la topología existente y, a continuación, haga clic en **Guardar** .

4.  Expanda el sitio donde desee agregar el director, haga clic con el botón secundario en **Grupos de servidores de director** y, a continuación, haga clic en **Nuevo grupo de servidores de director** .

5.  En el cuadro de diálogo **Definir el FQDN del grupo director** , haga lo siguiente:
    
      - En **FQDN del grupo de servidores** , escriba el FQDN del grupo de servidores de director.
    
      - Haga clic en **Grupo de servidores de varios equipos** y, a continuación, haga clic en **Siguiente** .

6.  En el cuadro de diálogo para **definir los equipos de este grupo** , haga lo siguiente:
    
      - Especifique el FQDN de equipo del primer miembro del grupo y haga clic en **Agregar** .
    
      - Repita el paso anterior para cada equipo que quiera agregar. Cuando haya acabado, haga clic en **Siguiente** .

7.  En el cuadro de diálogo para **definir el recurso compartido de archivos** cuadro de diálogo, realice una de las siguientes opciones:
    
      - Para usar un recurso compartido de archivos existente, haga clic en **Usar un recurso compartido de archivos definido previamente** , seleccione un recurso compartido de la lista y, a continuación, haga clic en **Siguiente** .
    
      - Para crear un nuevo recurso compartido de archivos, haga clic en **Definir un nuevo recurso compartido de archivos** , escriba el FQDN de la ubicación del recurso compartido de archivos en **FQDN de servidor de archivos** , escriba el nombre del recurso compartido en **Recurso compartido de archivos** y haga clic en **Siguiente** .
    
    > [!IMPORTANT]  
    > El recurso compartido de archivo que especifique o cree en este paso debe existir o crearse antes de publicar la topología.<br />
    > El recurso compartido de archivos asignado a un Director no se utiliza realmente, por lo que puede asignar el recurso compartido de archivos de cualquier grupo de servidores de la organización.


8.  En el cuadro de diálogo para **especificar la dirección URL de servicios Web** , en la **dirección URL base externa** , especifique el nombre completo para los directores y, a continuación, haga clic en **Finalizar** .
    
    > [!IMPORTANT]  
    > El nombre debe poder resolverse en servidores DNS de Internet y debe apuntar a la dirección IP pública del proxy inverso, que escucha las solicitudes HTTP/HTTPS enviadas a la dirección URL y lo envía mediante proxy al directorio virtual de servicios web externos del grupo de servidores de director.
    
    
    > [!WARNING]  
    > Si tiene más de un Grupo de servidores front-end o Servidor front-end los servicios Web externos FQDN deben ser únicos. Por ejemplo, si define los servicios Web externos FQDN de un Servidor front-end como <strong>pool01.contoso.com</strong> no puede usar <strong>pool01.contoso.com</strong> para otro Grupo de servidores front-end o Servidor front-end. Si también está implementando Directores, los servicios Web externos FQDN definidos para un Director o Grupo de directores deben ser diferentes de otro Director o Grupo de directores al igual que cualquier Grupo de servidores front-end o Servidor front-end. Si decide omitir los servicios Web externos con un FQDN autodefinido, todos los FQDN deben ser diferentes de otros Grupo de servidores front-end, Director o Grupo de directores.
    


9.  Publique la topología.

