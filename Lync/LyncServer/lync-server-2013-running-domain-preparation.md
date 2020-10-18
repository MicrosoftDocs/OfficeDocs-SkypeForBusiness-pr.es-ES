---
title: 'Lync Server 2013: ejecución de la preparación del dominio'
description: 'Lync Server 2013: ejecución de la preparación del dominio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2c4ebe94d07ed2d1fd9be013cd8e88204312f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577786"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a>Ejecutar la preparación del dominio para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-16_

Puede usar los cmdlets del shell de administración de Lync Server o de instalación para preparar los dominios. El cmdlet que prepara un dominio es **Enable-CsAdDomain**.

La preparación del dominio es el último paso en la preparación de los servicios de dominio de Active Directory para Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Para preparar dominios durante la instalación

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.

2.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación de Lync Server.

3.  Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.

4.  En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.

5.  En la página **Preparar el dominio**, haga clic en **Siguiente**.

6.  En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.

7.  En la columna **acción** , expanda **preparación del dominio**, busque un **\<Success\>** resultado de ejecución al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

8.  Espere a que se complete la replicación de Active Directory o fuerce la replicación en todos los controladores de dominio indicados en el complemento Sitios y servicios de Active Directory para el controlador de dominio raíz del bosque.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Para usar cmdlets para preparar el dominio

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo Admins. del dominio.

2.  Instale los componentes principales de Lync Server de la siguiente manera:
    
    1.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.
    
    3.  El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.
    
    4.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**. El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

4.  Realizar
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Por ejemplo:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Si no especifica el parámetro de dominio, el valor predeterminado es el dominio local.

5.  Compruebe que la preparación del dominio se ha realizado correctamente. Ejecute:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Por ejemplo:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > El parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se guarda en el contenedor del sistema (habitual en implementaciones de actualización cuyas opciones de configuración globales no se han migrado al contenedor de configuración), deberá definir un controlador de dominio en la raíz del bosque de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet presupone que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de AD &nbsp; DS.

    
    </div>
    
    Si no especifica el parámetro **Domain** , el valor predeterminado es el dominio local.
    
    Este cmdlet devuelve un valor de **LC \_ DOMAINSETTINGS \_ estado \_ Ready** si la preparación del dominio se ha realizado correctamente.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Uso de cmdlets para invertir la preparación del dominio para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

