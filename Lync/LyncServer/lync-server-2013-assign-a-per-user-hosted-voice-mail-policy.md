---
title: "Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013"
TOCTitle: "Attr. une strat. de mess. voc. hébergée par utilisateur dans Lync Server 2013"
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48276782
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013

 

_**Última modificación del tema:** 2010-11-07_

Implementar una o varias directivas de correo de voz que hospeda el usuario es opcional. Si no implementa las directivas por usuario, es preciso que las asigne explícitamente a objetos de usuario, grupo o contacto.

Para más información sobre la asignación o la eliminación de la asignación de directivas del correo de voz que hospeda el usuario, consulte la documentación de Shell de administración de Lync Server para los cmdlets siguientes:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## Para asignar una directiva de correo de voz que hospeda el usuario:

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Grant-CsHostedVoicemailPolicy para asignar la directiva de correo de voz que hospeda el usuario a objetos contacto, usuarios individuales y grupos. Por ejemplo, ejecute lo siguiente:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    En este ejemplo hemos asignado la directiva de correo de voz hospedado ExRedmond al usuario Antonio Bermejo.
    
    **Identity** especifica la cuenta de usuario que se debe modificar. El valor de Identity puede especificarse con cualquiera de los formatos siguientes:
    
      - La dirección SIP del usuario
    
      - El nombre principal de usuario de Active Directory del usuario
    
      - El nombre con formato dominio\\nombre del usuario (por ejemplo, contoso\\antoniobermejo)
    
      - El nombre para mostrar de Servicios de dominio de Active Directory (por ejemplo, Antonio Bermejo). Si usa el nombre para mostrar como valor de Identity, puede usar el asterisco (\*) como carácter comodín. Por ejemplo, el parámetro Identity "\* Escolar" devuelve todos los usuarios con un nombre para mostrar que termina con el valor de cadena de caracteres "Escolar".
    

    > [!NOTE]
    > El nombre de cuenta SAM de Active Directory del usuario no se puede usar como valor de Identity porque puede que no sea único en el bosque.


