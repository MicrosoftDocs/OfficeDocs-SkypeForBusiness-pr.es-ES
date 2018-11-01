---
title: "Crear o modificar un número de acceso para conferencias de acceso telefónico local"
TOCTitle: Crear o modificar un número de acceso para conferencias de acceso telefónico local
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48274324
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar un número de acceso para conferencias de acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-17_

Siga estos pasos si desea crear o modificar un número de acceso telefónico a conferencias.

> [!IMPORTANT]  
> Antes de crear un nuevo número de acceso telefónico, debe establecer una región de conferencias telefónicas en el plan de marcado asociado al número de acceso telefónico. Se pueden usar varios planes de marcado para la misma región.



## Para crear o modificar un número de acceso telefónico

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.

4.  En la página **Número de acceso telefónico**, siga uno de estos procedimientos:
    
      - Haga clic en **Nuevo** para abrir **Nuevo número de acceso telefónico**.
    
      - Seleccione uno de los números de acceso telefónico de la lista, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
        

        > [!NOTE]
        > Usar el campo de búsqueda para buscar el contenido de una columna de la lista de números de acceso telefónico no siempre permite obtener los resultados esperados. En lugar de eso, ordene la lista por la columna que le interese para identificar el número de acceso telefónico que desea ver o modificar.



5.  En **Número para mostrar**, escriba el número de teléfono que los usuarios de RTC (Red telefónica conmutada) marcan para unirse a una conferencia.
    

    > [!NOTE]
    > Este número se muestra en las invitaciones a la reunión y en la página web de las configuraciones de conferencias de acceso telefónico.



6.  En **Nombre para mostrar**, escriba una descripción del número de acceso telefónico. Es el nombre que se asocia al número de acceso telefónico en los resultados de búsqueda de Lync.
    

    > [!NOTE]
    > Este nombre se muestra en el cliente cuando un usuario llama al número de acceso.



7.  En **URI de línea**, escriba el número E.164 del número de acceso telefónico en el formato de URI TEL, con el símbolo + delante del número y sin espacios. Por ejemplo, tel:+14255550200.
    

    > [!NOTE]
    > El mismo URI de línea no puede volver a usarse por otro número de acceso telefónico a conferencias.



8.  En **URI del SIP**, siga este procedimiento:
    
      - En el cuadro siguiente, escriba un URI del SIP único para este número de acceso telefónico a conferencias. Este URI del SIP se muestra en varias ubicaciones, incluidos, pero sin limitarse a, los mensajes de notificación de llamadas y versiones anteriores de clientes de Communicator.
        

        > [!NOTE]
        > El mismo URI del SIP no puede volver a usarse por otro número de acceso telefónico a conferencias. El URI del SIP no puede modificarse una vez creado el número de acceso. El único modo de cambiar el URI del SIP es eliminar y volver a crear el número de acceso.

    
      - En el cuadro de lista desplegable, haga clic en el dominio de Aplicación Operador de conferencia que admite el número de acceso telefónico.

9.  En **Grupo de servidores**, haga clic en el grupo que ejecuta la instancia del operador de conferencia que admite el número de acceso telefónico.
    

    > [!NOTE]
    > Si necesita cambiar el grupo de servidores tras crear el número de acceso, deberá usar el cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> o eliminar y volver a crear el número de acceso.



10. En **Idioma principal**, haga clic en el idioma en el que se mostrarán las indicaciones para este número de acceso telefónico.
    

    > [!NOTE]
    > El idioma principal es el idioma que usa el operador de conferencia para responder la llamada. Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la página web de configuración de conferencias de acceso telefónico.



11. (Opcional) En **Idiomas secundarios (cuatro máximo)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales que desee poner a disposición de los que llaman a este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.
    

    > [!NOTE]
    > Puede seleccionar hasta cuatro idiomas secundarios para cada número acceso telefónico. Los usuarios pueden seleccionar un idioma secundario antes de especificar el ID de conferencia cuando marcan para acceder a una conferencia.



12. Para agregar una región para el número de acceso telefónico, en **Regiones asociadas**, haga clic en **Agregar**, seleccione una o más regiones para asociar a los planes de marcado del número de acceso telefónico y, a continuación, haga clic en **Aceptar**.

13. Para eliminar una región del número de acceso telefónico, en **Regiones asociadas**, seleccione la región que desea eliminar y haga clic en **Quitar**.

14. Haga clic en **Confirmar**.

