---
title: 'Lync Server 2013: ejecución de la preparación del esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12dda05b36406e620c08abac494dceecc7d314d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Ejecución de la preparación del esquema de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Puede usar los cmdlets del shell de administración de Lync Server o de instalación para preparar el esquema de Active Directory. El cmdlet que permite extender el esquema de Active Directory es **Install-CsAdServerSchema**.

<div>


> [!NOTE]  
> El cmdlet de preparación del esquema (<STRONG>Install-CsAdServerSchema</STRONG>) debe tener acceso al maestro de esquema, que requiere que el servicio del Registro remoto esté en ejecución y que la clave del Registro remoto esté habilitada. Si el servicio del Registro remoto no se puede habilitar en el maestro de esquema, puede ejecutar el cmdlet de forma local en el maestro de esquema. Para obtener más información acerca del acceso remoto al registro, consulte el artículo 314837 de Microsoft Knowledge base, "How to Manage Remote <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>Access to the Registry", en.



</div>

Una vez preparado el esquema, compruebe manualmente que la división del esquema se haya replicado antes de continuar con la preparación del bosque. Para obtener información detallada, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Para preparar el esquema del bosque actual durante la instalación

1.  Inicie sesión en un servidor del bosque como miembro del grupo Administradores de esquema y con derechos de administrador en el maestro de esquema.

2.  Desde el medio o la carpeta de instalación 2013 de Lync Server, ejecute setup. exe para iniciar el Asistente para la implementación.

3.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.

4.  El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.

5.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**.

6.  El instalador instala los componentes principales de Lync Server.

7.  Cuando el Asistente para la implementación esté listo, haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

8.  En **Paso 1: Preparar el esquema**, haga clic en **Ejecutar**.

9.  En la página **Preparar el esquema**, haga clic en **Siguiente**.

10. En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.

11. En la columna **acción** , expanda **preparación del esquema**, busque el resultado de la ** \<ejecución\> correcta** al final de cada tarea para comprobar que la preparación del esquema se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

12. Espere a que la replicación de Active Directory finalice o fuerce la replicación.

13. Compruebe manualmente que los cambios realizados en el esquema se hayan replicado al resto de controladores de dominio. Para obtener información detallada, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Para usar cmdlets para preparar el esquema del bosque actual

1.  Inicie sesión en un equipo del bosque como miembro del grupo Administradores de esquema y con derechos de administrador en el maestro de esquema.

2.  Instale los componentes principales de Lync Server de la siguiente manera:
    
    1.  Desde el medio o la carpeta de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.
    
    3.  El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.
    
    4.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**. El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

4.  Realizar
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Si no especifica el parámetro ldf, el valor predeterminado es la ruta de instalación de Lync Server 2013 que se lee en el registro.
    
    Por ejemplo:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Use el siguiente cmdlet para comprobar que la preparación del esquema ha finalizado correctamente.
    
        Get-CsAdServerSchema 
    
    Este cmdlet devuelve un valor de **estado\_\_de\_versión de esquema actual** si la preparación del esquema se realizó correctamente.

6.  Espere a que la replicación de Active Directory finalice o fuerce la replicación.

7.  Compruebe manualmente que los cambios realizados en el esquema se hayan replicado al resto de controladores de dominio. Para obtener información detallada, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Consulta también


[Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Preparar el esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

