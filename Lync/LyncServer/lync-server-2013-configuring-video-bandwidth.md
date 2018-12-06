---
title: Configuración de ancho de banda de vídeo en Lync Server 2013
TOCTitle: Configuración de ancho de banda de vídeo en Lync Server 2013
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48275123
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de ancho de banda de vídeo en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-02_

Lync Server 2013 incluye varios parámetros de configuración para la administración de vídeo para las llamadas entre dos entidades y conferencias entre varias entidades. Al implementar Lync Server 2013, debe evaluar si la configuración predeterminada es la adecuada para la organización y modificarla según sea necesario.

Los parámetros descritos en esta sección se aplican a las llamadas entre dos entidades y a las conferencia entre varias entidades. Vea o modifique estos parámetros con uno de los cmdlets siguientes:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Compruebe los siguientes parámetros en la directiva de conferencias:

  - **VideoBitRateKb**   Este parámetro especifica la velocidad de bits de vídeo máxima en kilobits por segundo (kbps) usados para el vídeo enviado por un usuario. El valor predeterminado es 50.000 kbps. Los valores válidos son 0 a 50.000.
    
    Este parámetro se aplica por separado al vídeo principal y al vídeo panorámico.
    
    Por ejemplo: si especifica 2.000 kbps, Lync Server puede enviar 2.000 kbps para la secuencia de vídeo principal y 2.000 kbps para la secuencia de vídeo panorámico.
    

    > [!NOTE]
    > El ancho de banda de red de vídeo máximo para un extremo de Lync 2013 es 8.000 kbps para el vídeo principal y 2.500 kbps para el vídeo panorámico. Estos valores máximos solo se alcanzan si se reciben o envían varios vídeos. Para más información, vea la sección "Uso de la red para el tráfico de medios" en<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Requisitos de ancho de banda de red para el tráfico multimedia de Lync Server 2013</A>. Esta sección muestra el ancho de banda máximo y típico para secuencias de vídeo en todas las resoluciones compatibles.



  - **TotalReceiveVideoBitRateKb**   Este parámetro, que es nuevo en Lync Server 2013, especifica la máxima velocidad de bits permitida (en kilobits por segundo) para todas las secuencias de vídeo recibidas por un cliente. Es decir, especifica el total combinado de todas las secuencias de vídeo, excepto las secuencias de vídeo panorámico, que puede recibir un cliente. Por ejemplo, si especifica 1.500 kbps, un cliente puede recibir hasta 1.500 kbps de vídeo, que puede componerse de varias secuencias de vídeo o una secuencia de vídeo única. Este parámetro solo se aplica a clientes de Lync Server 2013.
    
    El valor predeterminado para **TotalReceiveVideoBitRateKb** es 50.000 kbps. Si el parámetro **EnableMultiviewJoin** para Vista Galería se establece en True, **TotalReceiveVideoBitRateKb** no debe establecer por debajo de 420 kbps. Si el parámetro **EnableMultiviewJoin** para Vista Galería se establece en False, **TotalReceiveVideoBitRateKb** no debe establecerse por debajo de 100 kbps. Si **EnableMultiviewJoin** se establece en True y establece el valor por debajo de 420 kbps, los valores serán el valor del umbral de forma predeterminada. Este umbral ayuda a evitar errores accidentales que podrían resultar en una experiencia de usuario deficiente.
    

    > [!NOTE]
    > Para detalles sobre el parámetro <STRONG>EnableMultiviewJoin</STRONG>, vea <A href="lync-server-2013-configuring-gallery-view.md">Configuración de la vista de galería</A>.



  - **MaxVideoConferencingResolution**   Este parámetro ya no se usa en clientes de Lync Server 2013 en conferencias de Lync Server 2013. Las conferencias de Lync Server 2013 usan los controles de velocidad de bits se ha descrito anteriormente en esta sección. Este parámetro todavía se usa en clientes heredados al unirse a una conferencia de Lync Server 2013. Este parámetro determina la resolución máxima permitida para los clientes heredados en conferencias organizadas por los usuarios que alojados en Lync Server 2013. Es decir, los clientes heredados se tratan de la misma forma que en versiones anteriores de Lync Server o Office Communications Server.

Además de los parámetros de la directiva de conferencias que se aplican a los usuarios, evalúe los parámetros de configuración de los medios. Vea o modifique estos parámetros con uno de los cmdlets siguientes:

  - **Get-CsMediaConfiguration**

  - **Set- CsMediaConfiguration**

  - **New- CsMediaConfiguration**

Compruebe la siguiente configuración:

  - **MaxVideoRateAllowed**   Esta configuración por grupo especifica la frecuencia máxima a la que se transferirán las señales de vídeo en los extremos del cliente. Solo se aplica a las versiones anteriores de clientes de Lync Server.
    

    > [!NOTE]
    > Los clientes de Lync Server 2013 ignoran este parámetro y, en su lugar, usan el parámetro TotalReceiveVideoBitRateKb en la directiva de conferencias.

    
    El valor predeterminado es HD720P. Los valores válidos son HD720p15M, VGA600K y CIF250K.
    
    Por ejemplo: si especifica 1.500 kbps, todos los clientes heredados del grupo pueden recibir hasta 1.500 kbps de vídeo en conferencias entre dos o entre varias entidades.

Los siguientes procedimientos son ejemplos del uso de Shell de administración de Lync Server para modificar los parámetros descritos en esta sección.

## Para modificar la directiva de conferencias para la configuración de vídeo

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para cambiar la directiva de conferencia:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

## Para modificar la configuración de medios para los clientes heredados

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  En la línea de comandos, ejecute el cmdlet siguiente para cambiar la configuración de medios:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

