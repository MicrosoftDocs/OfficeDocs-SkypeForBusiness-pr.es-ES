---
title: 'Lync Server 2013: Ejecutar la preparación del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fdd01b15fe5858129300c3a9f2f26c3d3de672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Ejecutar la preparación del dominio para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-16_

Puede usar los cmdlets del shell de administración de Lync Server o de instalación para preparar los dominios. El cmdlet que prepara un dominio es **enable-CsAdDomain**.

La preparación del dominio es el último paso en la preparación de los servicios de dominio de Active Directory para Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Para usar el programa de instalación para preparar dominios

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo administradores de dominio.

2.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.

3.  Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

4.  En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.

5.  En la página **preparar el dominio** , haga clic en **siguiente**.

6.  En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.

7.  En la columna **acción** , expanda **preparar el dominio**, busque un ** \<\> ** resultado de ejecución correcta al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

8.  Espere a que se complete la replicación de Active Directory o fuerce la replicación en todos los controladores de dominio que aparecen en el complemento sitios y servicios de Active Directory para el controlador de dominio raíz del bosque.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Para usar cmdlets para preparar el dominio

1.  Inicie sesión en cualquier servidor del dominio como miembro del grupo administradores de dominio.

2.  Instale los componentes básicos de Lync Server de la siguiente manera:
    
    1.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el redistribuible de Microsoft Visual C++, haga clic en **sí**.
    
    3.  En el cuadro de diálogo instalación de Lync Server 2013 se le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o **Desplácese** hasta la ubicación que desee y, a continuación, haga clic en **instalar**.
    
    4.  En la página contrato de licencia, seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar**. El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

4.  Ejecute:
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Por ejemplo:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.

5.  Comprobar que la preparación del dominio se completó correctamente. Ejecute:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Por ejemplo:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > El parámetro GlobalSettingsDomainController le permite indicar dónde se almacena la configuración global. Si la configuración se almacena en el contenedor del sistema (que es habitual en las implementaciones de actualización que no han tenido la configuración global migrada al contenedor de configuración), se define un controlador de dominio en la raíz del bosque de Active Directory. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet supone que la configuración se almacena en el contenedor de configuración y se refiere a cualquier controlador de dominio&nbsp;de AD DS.

    
    </div>
    
    Si no especifica el parámetro **Domain** , el valor predeterminado es el dominio local.
    
    Este cmdlet devuelve un valor de **LC\_DOMAINSETTINGS\_estado\_listo** si la preparación del dominio se realizó correctamente.

</div>

<div>

## <a name="see-also"></a>Vea también


[Uso de cmdlets para revertir la preparación del dominio para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

