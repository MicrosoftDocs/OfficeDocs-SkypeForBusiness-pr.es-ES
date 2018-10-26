---
title: 'Lync Server 2013: Asociar una subred a un sitio de red'
TOCTitle: Asociar una subred a un sitio de red
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48276311
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asociar una subred a un sitio de red en Lync Server 2013

 

_**Última modificación del tema:** 2014-10-20_

Todas las subredes de la red deben estar asociadas con un sitio de red específico. Esto se debe a que la información de la subred se usa para determinar el sitio de red en el que reside un extremo mientras se inicia una nueva sesión. Cuando se conoce la ubicación de cada parte en una sesión, las características avanzadas de Telefonía IP empresarial pueden aplicar esta información para determinar cómo administrar la configuración o el enrutamiento de las llamadas.

> [!IMPORTANT]  
> Todas las direcciones IP públicas de los servidores perimetrales de audio y vídeo en la implementación deben incluirse en los parámetros de configuración de red. Estas direcciones IP se agregan como subredes con una máscara de 32. El sitio de red asociado debe corresponder con el sitio de red configurado adecuado. Por ejemplo, la dirección IP pública que corresponde a los servidores perimetrales A/V en el sitio central Chicago sería NetworkSiteID Chicago. Para más información sobre las direcciones IP públicas, consulte <a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013</a> en la documentación sobre planeación.




> [!NOTE]
> Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas. A continuación se ofrece la información de alerta relevante y un ejemplo:<BR><STRONG>Origen :</STRONG> Servicio de directivas de ancho de banda CS (núcleo)<BR><STRONG>Número de evento :</STRONG> 36034<BR><STRONG>Nivel :</STRONG> 2<BR><STRONG>Descripción :</STRONG> las subredes de las siguientes direcciones IP: &lt;La lista de direcciones IP&gt; no está configurada o las subredes no están asociadas a un sitio de red.<BR><STRONG>Causa :</STRONG> las subredes de las correspondientes direcciones IP faltan en las opciones de configuración de la red o las subredes no están asociadas a un sitio de red.<BR><STRONG>Solución :</STRONG> agregue subredes correspondientes a la lista de direcciones IP en los parámetros de configuración de red y asocie todas las subredes a un sitio de red.<BR>Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera: 
> <OL>
> <LI>
> <P>Asegúrese de que la dirección IP 10.121.248.226 está asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 está asociada a la subred 10.121.249.0/24.</P>
> <LI>
> <P>Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 está asociada a un sitio de red.</P></LI></OL>



Para más información sobre cómo trabajar con subredes de red, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:

  - [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)

> [!TIP]  
> Si trabaja con un gran número de subredes, es aconsejable usar un archivo CSV (valores separados por comas) para asociar las subredes a los sitios. El archivo CSV debe tener las cuatro columnas siguientes: <strong>IPAddress</strong>, <strong>mask</strong>, <strong>description</strong>, <strong>NetworkSiteID</strong>.



## Para asociar una subred a un sitio de red mediante el Shell de administración

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsNetworkSubnet** para asociar una subred a un sitio de red:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Por ejemplo:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    En este ejemplo, ha creado una asociación entre la subred 172.11.12.13 y el sitio de red “Chicago”.

3.  Repita el paso 2 para todas las subredes de la topología.

## Para asociar subredes a sitios de red mediante la importación de un archivo CSV

1.  Cree un archivo CSV que incluya todas las subredes que quiera agregar. Por ejemplo, cree un archivo denominado **subnet.csv** con el contenido siguiente:
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute el siguiente cmdlet para importar **subnet.csv** y almacene su contenido en el almacén de administración Lync Server:
    
        import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

## Para asociar una subred a un sitio de red mediante el Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red** .

3.  Haga clic en el botón de navegación **Subred** .

4.  Haga clic en **Nuevo** .

5.  En la página **Nueva subred** , haga clic en **Id. de subred** y escriba la primera dirección en el intervalo de direcciones IP definido mediante la subred que quiere asociar al sitio de red.

6.  Haga clic en **Máscara** y escriba la máscara de bits que quiere aplicar a la subred.

7.  Haga clic en **Id. de sitio de red** y seleccione el identificador de sitio del sitio al que agrega esta subred.
    

    > [!NOTE]
    > Si todavía no ha creado sitios de red, esta lista estará vacía. Consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">Crear o modificar un sitio de red en Lync Server 2013</A> para ver más detalles sobre el procedimiento. También puede recuperar identificadores de sitio para su implementación mediante la ejecución del cmdlet <STRONG>Get-CsNetworkSite</STRONG>. Para más información, consulte la documentación de Shell de administración de Lync Server.



8.  Si lo desea, haga clic en **Descripción** y escriba información adicional para describir esta subred.

9.  Haga clic en **Confirmar** .

Repita estos pasos para agregar otras subredes a un sitio de red.

