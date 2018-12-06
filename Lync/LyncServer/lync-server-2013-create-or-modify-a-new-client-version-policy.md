---
title: Crear o modificar una nueva directiva de versión de cliente
TOCTitle: Crear o modificar una nueva directiva de versión de cliente
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ898476(v=OCS.15)
ms:contentKeyID: 52061634
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una nueva directiva de versión de cliente

 

_**Última modificación del tema:** 2013-02-23_

Puede usar directivas de versión de cliente para especificar las versiones de cliente admitidas en el entorno. Con el control de versiones de cliente, puede reducir los costos que conlleva la compatibilidad con varias versiones de cliente. También puede mejorar la experiencia del usuario global, ya que cuando interactúan versiones de cliente antiguas y nuevas, las características disponibles pueden verse limitadas por las versiones más antiguas. Puede crear o modificar las directivas de versión de cliente desde Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.

## Para crear o modificar directivas de versión de cliente mediante Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes**.
    

    > [!NOTE]
    > La pestaña <STRONG>Directiva de versión de cliente</STRONG> está seleccionada de forma predeterminada.



4.  En la página **Directiva de versión de cliente**, siga uno de estos procedimientos:
    
      - Para crear una directiva de versión de cliente, haga clic en **Nueva**, seleccione **Directiva del sitio**, **Directiva de grupo de servidores** o **Directiva de usuario** y, a continuación, haga clic en **Aceptar**.
    
      - Para modificar la directiva global u otra directiva de versión de cliente existente, seleccione la directiva, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  En la página **Editar directiva de versión de cliente**, cree o modifique las reglas, tal como se describe en [Crear o modificar una nueva regla de directiva de versión de cliente](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

## Creación o modificación de directivas de versión de cliente mediante cmdlets de Windows PowerShell

Puede crear directivas de versión de cliente mediante el cmdlet **New-CsClientVersionPolicy** y modificarlas mediante el cmdlet **Set-CsClientVersionPolicy**. Estos cmdlets se pueden ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para crear una nueva directiva de versión de cliente con ámbito de sitio

  - El siguiente comando crea una nueva directiva de versión de cliente aplicada al sitio Redmond. No se especifican parámetros adicionales, por lo que la nueva directiva usará la configuración de versión de cliente predeterminada.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

## Para crear una nueva directiva de versión de cliente por usuario

  - Para crear una directiva por usuario, use un comando similar al siguiente:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

Para obtener detalles, consulte los temas de Ayuda acerca de los cmdlets [New-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionPolicy) y [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy).

