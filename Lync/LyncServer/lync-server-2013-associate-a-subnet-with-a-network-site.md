---
title: 'Lync Server 2013: Asociar una subred a un sitio de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f54ba8be2be6ae042633e519c5d7d27bde834162
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Asociar una subred a un sitio de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Cada subred de su red debe estar asociada con un sitio de red específico, ya que la información de subred se usa para determinar el sitio de red en el que se encuentra un punto final mientras se inicia una nueva sesión. Cuando se conoce la ubicación de cada una de las partes de una sesión, las características de telefonía IP avanzada pueden aplicarla para determinar cómo manejar la configuración o el enrutamiento de las llamadas.

<div>


> [!IMPORTANT]  
> Todas las direcciones IP públicas de los servidores perimetrales de audio y vídeo en la implementación deben incluirse en los parámetros de configuración de red. Estas direcciones IP se agregan como subredes con una máscara de 32. El sitio de red asociado debe corresponder con el sitio de red configurado adecuado. Por ejemplo, la dirección IP pública que corresponde al servidor perimetral A/V en el sitio central de Chicago sería NetworkSiteID Chicago. Para obtener detalles sobre las direcciones IP públicas, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013</A> en la documentación de planeación.



</div>

<div>


> [!NOTE]  
> Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas. A continuación se ofrece la información de alerta relevante y un ejemplo:<BR><STRONG>Fuente:</STRONG> Servicio de directivas de ancho de banda CS (núcleo)<BR><STRONG>Número de evento:</STRONG> 36034<BR><STRONG>Nivel:</STRONG> 2<BR><STRONG>Descripción:</STRONG> Las subredes de las siguientes direcciones IP: &lt;la lista de direcciones&gt; IP no está configurada o las subredes no están asociadas a un sitio de red.<BR><STRONG>Causa:</STRONG> Las subredes de las direcciones IP correspondientes no se encuentran en la configuración de red o las subredes no están asociadas a un sitio de red.<BR><STRONG>Solución:</STRONG> Agregue subredes que correspondan a la lista de direcciones IP en la configuración de red y asocie cada subred a un sitio de red.<BR>Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera: 
> <OL>
> <LI>
> <P>Asegúrese de que la dirección IP 10.121.248.226 esté asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 esté asociada a la subred 10.121.249.0/24.</P>
> <LI>
> <P>Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 esté asociada a un sitio de red.</P></LI></OL>



</div>

Para obtener más información sobre cómo trabajar con subredes de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> Si trabaja con un gran número de subredes, le recomendamos que use un archivo de valores separados por comas (CSV) para asociar las subredes a los sitios. El archivo CSV debe tener las cuatro columnas siguientes: <STRONG>IPAddress</STRONG>, <STRONG>Mask</STRONG>, <STRONG>Description</STRONG>, <STRONG>NetworkSiteID</STRONG>.



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>Para asociar una subred a un sitio de red mediante el shell de administración

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsNetworkSubnet** para asociar una subred a un sitio de red:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Por ejemplo:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    En este ejemplo, ha creado una asociación entre la subred 172.11.12.13 y el sitio de red “Chicago”.

3.  Repita el paso 2 para todas las subredes de la topología.

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Para asociar subredes a sitios de red mediante la importación de un archivo CSV

1.  Cree un archivo CSV que incluya todas las subredes que quiera agregar. Por ejemplo, cree un archivo denominado   **subnet.csv** con el contenido siguiente:
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute el siguiente cmdlet para importar **subnet. csv**y, a continuación, almacene su contenido en el almacén de administración de Lync Server:
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Para asociar una subred a un sitio de red mediante el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Subred**.

4.  Haga clic en **Nuevo**.

5.  En la página **Nueva subred**, haga clic en **Id. de subred** y escriba la primera dirección en el intervalo de direcciones IP definido mediante la subred que quiere asociar al sitio de red.

6.  Haga clic en **Máscara** y escriba la máscara de bits que quiere aplicar a la subred.

7.  Haga clic en **Id. de sitio de red** y seleccione el identificador de sitio del sitio al que agrega esta subred.
    
    <div>
    

    > [!NOTE]  
    > Si todavía no ha creado sitios de red, esta lista estará vacía. Para obtener más información sobre el procedimiento, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>. También puede recuperar identificadores de sitio para implementarlos ejecutando el cmdlet <STRONG>Get-CsNetworkSite</STRONG>. Para obtener más información, consulte la documentación del shell de administración de Lync Server.

    
    </div>

8.  Si lo desea, haga clic en **Descripción** y escriba información adicional para describir esta subred.

9.  Haga clic en **Confirmar**.

Repita estos pasos para agregar otras subredes a un sitio de red.

</div>

</div>

<span> </span>

</div>

</div>

</div>

