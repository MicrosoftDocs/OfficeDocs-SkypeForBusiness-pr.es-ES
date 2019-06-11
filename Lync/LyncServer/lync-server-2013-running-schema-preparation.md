---
title: 'Lync Server 2013: Ejecutar la preparación del esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Ejecutar la preparación del esquema de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Puede usar el programa de instalación o los cmdlets del shell de administración de Lync Server para preparar el esquema de Active Directory. El cmdlet que extiende el esquema de Active Directory es **install-CsAdServerSchema**.

<div>


> [!NOTE]  
> El cmdlet de preparación del esquema (<STRONG>install-CsAdServerSchema</STRONG>) debe tener acceso al maestro de esquema, que requiere que el servicio de registro remoto se esté ejecutando y que la clave del registro remoto esté habilitada. Si el servicio de registro remoto no se puede habilitar en el maestro de esquema, puede ejecutar el cmdlet localmente en el maestro de esquema. Para obtener más información sobre el acceso remoto al registro, consulte el artículo 314837 de Microsoft Knowledge base, "cómo administrar el acceso remoto <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>al registro" en.



</div>

Una vez completada la preparación del esquema, compruebe manualmente que la partición de esquema se ha replicado antes de continuar con la preparación del bosque. Para obtener más información, vea [comprobar la replicación de esquema de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Para usar el programa de instalación para preparar el esquema del bosque actual

1.  Inicie sesión en un servidor del bosque como miembro del grupo administradores de esquema y con derechos de administrador en el maestro de esquema.

2.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación.

3.  Si se le pide que instale el redistribuible de Microsoft Visual C++, haga clic en **sí**.

4.  En el cuadro de diálogo instalación de Lync Server 2013 se le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o **Desplácese** hasta la ubicación que desee y, a continuación, haga clic en **instalar**.

5.  En la página contrato de licencia, seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar**.

6.  El instalador instala los componentes principales de Lync Server.

7.  Cuando el Asistente para la implementación esté listo, haga clic en **preparar Active**Directory y, a continuación, espere a que se determine el estado de implementación.

8.  En el **paso 1: preparar el esquema**, haga clic en **Ejecutar**.

9.  En la página **preparar esquema** , haga clic en **siguiente**.

10. En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.

11. En la columna **acción** , expanda **preparar el esquema**, busque el resultado de ejecución ** \<correcta\> ** al final de cada tarea para comprobar que la preparación del esquema se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

12. Espere a que se complete la replicación de Active Directory o fuerce la replicación.

13. Compruebe manualmente que los cambios de esquema se han replicado en el resto de los controladores de dominio. Para obtener más información, vea [comprobar la replicación de esquema de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Para usar los cmdlets para preparar el esquema del bosque actual

1.  Inicie sesión en un equipo del bosque como miembro del grupo administradores de esquema y con derechos de administrador en el maestro de esquema.

2.  Instale los componentes básicos de Lync Server de la siguiente manera:
    
    1.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el redistribuible de Microsoft Visual C++, haga clic en **sí**.
    
    3.  En el cuadro de diálogo instalación de Lync Server 2013 se le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o **Desplácese** hasta la ubicación que desee y, a continuación, haga clic en **instalar**.
    
    4.  En la página contrato de licencia, seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar**. El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

4.  Ejecute:
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Si no especifica el parámetro ldf, el valor predeterminado es la ruta de instalación de Lync Server 2013 que se lee en el registro.
    
    Por ejemplo:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Use el siguiente cmdlet para comprobar que la preparación del esquema se ejecutó completamente.
    
        Get-CsAdServerSchema 
    
    Este cmdlet devuelve un valor de **estado\_\_de\_versión de esquema actual** si la preparación del esquema se realizó correctamente.

6.  Espere a que se complete la replicación de Active Directory o fuerce la replicación.

7.  Compruebe manualmente que los cambios de esquema se han replicado en el resto de los controladores de dominio. Para obtener más información, vea [comprobar la replicación de esquema de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

