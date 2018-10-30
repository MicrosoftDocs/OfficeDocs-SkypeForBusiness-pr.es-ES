﻿---
title: "Ejemplo de recopilación de requisitos de org. para control de admisión de llamadas"
TOCTitle: 'Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas'
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48274870
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Este ejemplo muestra cómo planear e implementar el control de admisión de llamadas (CAC). De forma general, esto consta de las siguientes actividades:

1.  Identificar todos los concentradores de red y redes troncales (llamados *regiones de red* ).

2.  Identificar el sitio central de Lync Server que administrará el CAC para cada región de red.

3.  Identificar y definir los *sitios de red* que están conectados a cada región de red.

4.  Para cada sitio de red cuya conexión a la red WAN tiene un ancho de banda restringido, describir la capacidad de ancho de banda de la conexión WAN y los límites de ancho de banda que el administrador ha establecido para el tráfico de medios de Lync Server, si procede. No es necesario incluir sitios cuya conexión a la red WAN no tiene ancho de banda restringido.

5.  Asociar cada subred de la red a un sitio de red.

6.  Asignar los vínculos entre las regiones de red. Para cada vínculo, describir su capacidad de ancho de banda y los límites que el administrador de la red haya establecido sobre el tráfico de medios de Lync Server.

7.  Definir una ruta entre cada par de regiones de red.

## Recopilar la información necesaria

Para preparar el control de admisión de llamadas, recopile la información descrita en los pasos siguientes:

1.  Identificar las regiones de red. Una región de red representa una red troncal de red o un concentrador de red.
    
    Una red troncal de red o un concentrador de red forma parte de una infraestructura de red informática que interconecta diversas partes de red, que proporciona una ruta de acceso para el intercambio de información entre distintas redes LAN o subredes. Una red troncal puede asociar diversas redes, desde una ubicación pequeña a una amplia zona geográfica. La capacidad de la red troncal suele ser mayor que la de las redes conectadas a ella.
    
    Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red incluye una colección de sitios de red. Trabaje con el administrador de la red para definir las regiones de red de su empresa.

2.  Identificar cada sitio central asociado a la región de red. Un sitio central contiene por lo menos un Servidor front-end y es la implementación de Lync Server que administrará el CAC para todo el tráfico de medios que pasa por la conexión WAN de la región de red.
    
    **Red de empresa de ejemplo dividida en tres regiones de red**
    
    ![Ejemplo de topología de red con 3 regiones de red](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Ejemplo de topología de red con 3 regiones de red")  
    

    > [!NOTE]
    > Una red de conmutación de etiquetas multiprotocolo (MPLS) debe representarse como una región de red en la que cada ubicación geográfica tiene un sitio de red correspondiente. Para obtener más información, consulte el tema “ <A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Control de admisión de llamadas en una red MPLS con Lync Server 2013</A>” en la documentación sobre planeación.

    
    En la topología de red de ejemplo anterior existen tres regiones de red, cada una con un sitio central de Lync Server que administra el CAC. El sitio central adecuado para una región de red se elige por la proximidad geográfica. Como el tráfico de medios será mayor dentro de las regiones de red, la propiedad por proximidad geográfica lo hace independiente y seguirá siendo funcional aunque otros sitios centrales dejen de estar disponibles.
    
    En este ejemplo, una implementación de Lync Server denominada Chicago es el sitio central de la región Norteamérica.
    
    Todos los usuarios de Lync en Norteamérica se hospedan en servidores de la implementación Chicago. En la tabla siguiente se muestran los sitios centrales de las tres regiones de red.
    
    ### Regiones de red y sus sitios centrales asociados
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Región de red</th>
    <th>Sitio central</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Norteamérica</p></td>
    <td><p>Chicago</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>Londres</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>Pekín</p></td>
    </tr>
    </tbody>
    </table>
    

    > [!NOTE]
    > Según la topología de Lync Server, un mismo sitio central puede asignarse a varias regiones de red.



3.  En cada región de red, identifique todos los sitios de red (oficinas o ubicaciones) cuyas conexiones WAN no tienen ancho de banda restringido. Como estos sitios no tienen ancho de banda restringido, no es necesario aplicarles directivas de ancho de banda de CAC.
    
    En el ejemplo que se muestra en la siguiente tabla, tres sitios de red no tienen vínculos WAN de ancho de banda restringido: Nueva York, Chicago y Detroit.
    
    ### Sitios de red no restringidos por el ancho de banda de WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sitio de red</th>
    <th>Región de red</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Nueva York</p></td>
    <td><p>Norteamérica</p></td>
    </tr>
    <tr class="even">
    <td><p>Chicago</p></td>
    <td><p>Norteamérica</p></td>
    </tr>
    <tr class="odd">
    <td><p>Detroit</p></td>
    <td><p>Norteamérica</p></td>
    </tr>
    </tbody>
    </table>


4.  En cada región de red, identifique todos los sitios de red que se conectan a la región de red a través de vínculos WAN de ancho de banda restringido.
    
    Para asegurar la calidad de audio y vídeo, se recomienda que estos sitios de red de ancho de banda restringido tengan las redes WAN supervisadas y directivas de ancho de banda del CAC que limiten el flujo del tráfico de medios (voz o vídeo) hacia la región de red y desde ella.
    
    En el ejemplo que se muestra en la siguiente tabla, hay tres sitios de red que están restringidos por el ancho de banda de WAN: Portland, Reno y Albuquerque.
    
    ### Sitios de red restringidos por el ancho de banda de WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sitio de red</th>
    <th>Región de red</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Norteamérica</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Norteamérica</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Norteamérica</p></td>
    </tr>
    </tbody>
    </table>
    
    **Región de red para CAC Norteamérica con tres sitios de red que no están restringidos por el ancho de banda (Chicago, Nueva York y Detroit) y tres sitios de red que están restringidos por el ancho de banda de WAN (Portland, Reno y Albuquerque)**
    
    ![Ejemplo de sitios de la red restringidos por el ancho de banda de la WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Ejemplo de sitios de la red restringidos por el ancho de banda de la WAN")  

5.  Para cada vínculo WAN de ancho de banda restringido, determine lo siguiente:
    
      - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio provoca que se exceda este límite, Lync Server no permite que se inicie la sesión.
    
      - Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.
    
      - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo provoca que se exceda este límite, Lync Server no permite que se inicie la sesión.
    
      - Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.
    
    ### Sitios de red con información de restricción de ancho de banda de WAN (ancho de banda en kbps)
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sitio de red</th>
    <th>Región de red</th>
    <th>Límite de ancho de banda</th>
    <th>Límite de audio</th>
    <th>Límite de sesión de audio</th>
    <th>Límite de vídeo</th>
    <th>Límite de sesión de vídeo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>5.000</p></td>
    <td><p>2.000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Nueva York</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    </tr>
    </tbody>
    </table>


6.  Para cada subred de la red, especifique el sitio de red asociado.
    
    > [!IMPORTANT]  
    > Cada subred de la red debe estar asociada a un sitio de red, aunque el sitio de red no esté restringido por el ancho de banda. Esto se debe a que el control de admisión de llamadas usa la información de la subred para determinar el sitio de red en que está situado un extremo. Cuando se determinan las ubicaciones de ambas partes de la sesión, el control de admisión de llamadas puede determinar si existe suficiente ancho de banda para establecer una llamada. Cuando se establece una sesión a través de un vínculo que no tiene límites de ancho de banda, se genera una alerta.<br />
    > Si implementa servidores perimetrales de audio/vídeo, las direcciones IP públicas de cada servidor perimetral deben estar asociadas al sitio de red en el que se implementa el servidor perimetral. Cada dirección IP pública del servidor perimetral A/V debe agregarse a las opciones de configuración de la red como subred con una máscara de subred de 32. Por ejemplo, si implementa servidores perimetrales A/V en Chicago, para cada dirección IP externa de los servidores, cree una subred con una máscara de subred de 32 y asocie el sitio de red Chicago a dichas subredes. Para obtener más información acerca de las direcciones IP públicas, consulte <a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013</a> en la documentación sobre planeación.
    

    > [!NOTE]
    > Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas. A continuación se ofrece la información de alerta relevante y un ejemplo:<BR><STRONG>Origen :</STRONG> Servicio de directivas de ancho de banda CS (núcleo)<BR><STRONG>Número de evento :</STRONG> 36034<BR><STRONG>Nivel :</STRONG> 2<BR><STRONG>Descripción :</STRONG> las subredes de las siguientes direcciones IP: &lt;List of IP Addresses&gt; no está configurada o las subredes no están asociadas a un sitio de red.<BR><STRONG>Causa :</STRONG> las subredes de las correspondientes direcciones IP faltan en las opciones de configuración de la red o las subredes no están asociadas a un sitio de red.<BR><STRONG>Solución :</STRONG> agregue las subredes correspondientes a la lista anterior de direcciones IP a las opciones de configuración y asocie cada subred a un sitio de red.<BR>Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera: 
    > <OL>
    > <LI>
    > <P>Asegúrese de que la dirección IP 10.121.248.226 está asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 está asociada a la subred 10.121.249.0/24.</P>
    > <LI>
    > <P>Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 está asociada a un sitio de red.</P></LI></OL>

    
    ### Sitios de red y subredes asociadas (ancho de banda en kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Sitio de red</th>
    <th>Región de red</th>
    <th>Límite de ancho de banda</th>
    <th>Límite de audio</th>
    <th>Límite de sesión de audio</th>
    <th>Límite de vídeo</th>
    <th>Límite de sesión de vídeo</th>
    <th>Subredes</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>5.000</p></td>
    <td><p>2.000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23, 172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>Nueva York</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>157.57.211.0/23, 172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>(sin límite)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  En el control de admisión de llamadas de Lync Server, las conexiones entre regiones de red se denominan *vínculos de región* . Para cada vínculo de región, determine lo siguiente, tal como hizo para los sitios de red:
    
      - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio provoca que se exceda este límite, Lync Server no permite que se inicie la sesión.
    
      - Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.
    
      - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo provoca que se exceda este límite, Lync Server no permite que se inicie la sesión.
    
      - Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.
    
    **Vínculos de región de red con límites de ancho de banda asociados**
    
    ![Ejemplo de limitaciones entre 3 regiones](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Ejemplo de limitaciones entre 3 regiones")  
    
    ### Información de ancho de banda de vínculos de región (ancho de banda en kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nombre del vínculo de región</th>
    <th>Primera región</th>
    <th>Segunda región</th>
    <th>Límite de ancho de banda</th>
    <th>Límite de audio</th>
    <th>Límite de sesión de audio</th>
    <th>Límite de vídeo</th>
    <th>Límite de sesión de vídeo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-LINK</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>EMEA</p></td>
    <td><p>50.000</p></td>
    <td><p>20.000</p></td>
    <td><p>175</p></td>
    <td><p>14.000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-LINK</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25.000</p></td>
    <td><p>10.000</p></td>
    <td><p>175</p></td>
    <td><p>7.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  Definir una ruta entre cada par de regiones de red.
    

    > [!NOTE]
    > Se requieren dos vínculos para la ruta entre las regiones Norteamérica y APAC porque no existe ningún vínculo de región que las conecte directamente.

    
    ### Rutas de región
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nombre de la ruta de región</th>
    <th>Primera región</th>
    <th>Segunda región</th>
    <th>Vínculos de región</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ROUTE</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>EMEA</p></td>
    <td><p>NA-EMEA-LINK</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-ROUTE</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC-LINK</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-ROUTE</p></td>
    <td><p>Norteamérica</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-LINK, EMEA-APAC-LINK</p></td>
    </tr>
    </tbody>
    </table>


9.  Para cada par de sitios de red que estén conectados directamente por un solo vínculo (denominado vínculo *entre sitios* ), determine lo siguiente:
    
      - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio provoca que se exceda este límite, Lync Server no permite que se inicie la sesión.
    
      - Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.
    
      - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo provoca que se exceda este límite, Lync Server no permite que se inicie la sesión.
    
      - Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.
    
    **Región de red para CAC Norteamérica con indicación de las capacidades de ancho de banda y los límites de ancho de banda del vínculo entre sitios entre Reno y Albuquerque**
    
    ![Ejemplo de sitios de la red restringidos por el ancho de banda de la WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Ejemplo de sitios de la red restringidos por el ancho de banda de la WAN")  
    
    ### Información de ancho de banda de un vínculo entre sitios entre dos sitios de red (ancho de banda en kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nombre del vínculo entre sitios</th>
    <th>Primer sitio</th>
    <th>Segundo sitio</th>
    <th>Límite de ancho de banda</th>
    <th>Límite de audio</th>
    <th>Límite de sesión de audio</th>
    <th>Límite de vídeo</th>
    <th>Límite de sesión de vídeo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-Intersite-Link</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>20.000</p></td>
    <td><p>12.000</p></td>
    <td><p>175</p></td>
    <td><p>5.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


## Siguientes pasos

Una vez recopilada la información necesaria, puede realizar la implementación del CAC mediante el Shell de administración de Lync Server o mediante Panel de control de Lync Server.


> [!NOTE]
> Aunque la mayoría de las tareas de configuración de red se pueden crear con Panel de control de Lync Server, para crear subredes y vínculos entre sitios, debe usar el Shell de administración de Lync Server. Para obtener más información, consulte la documentación del Shell de administración de Lync Server sobre el cmdlet <STRONG>New-CsNetworkSubnet</STRONG> y <STRONG>New-CsNetworkIntersitePolicy</STRONG>.


