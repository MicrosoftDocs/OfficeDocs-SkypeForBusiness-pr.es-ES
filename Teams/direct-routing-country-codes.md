---
title: Códigos de país de enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lea este artículo para ubicar los códigos de países de la ruta de medios para el enrutamiento directo.
ms.openlocfilehash: 4d3e19ceeab48e7ade6ffa9b51bff68f38613426
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836100"
---
# <a name="direct-routing-media-path-country-codes"></a>Códigos de países de ruta de medios de enrutamiento directo

Cuando se elige una ruta de enrutamiento para los medios, el enrutamiento directo, de forma predeterminada, asigna siempre un centro de recursos basado en la dirección IP pública del controlador de borde de sesión (SBC) y siempre selecciona la ruta más cercana al centro de recursos de SBC.

Sin embargo, en algunos casos, la ruta de acceso a los medios predeterminados puede no ser la ruta de acceso de medios óptima; por ejemplo, una IP pública de un intervalo de Estados Unidos puede asignarse a un SBC ubicado en Europa. 

Si usas el parámetro-MediaRelayRoutingLocationOverride con los cmdlets New-CsOnlinePSTNGateway y set-CsOnlinePSTNGateway, puedes especificar la región preferida para el tráfico de multimedia. Por ejemplo, el siguiente comando especifica que la región preferida es Alemania:

Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com – MediaRelayRoutingLocationOverride DE 

Tenga en cuenta que Microsoft solo recomienda establecer este parámetro si el registro de llamadas indica claramente que la asignación predeterminada del centro de recursos para la ruta multimedia no usa la ruta más cercana al centro de trabajo de SBC. 
 
## <a name="country-code-reference-table"></a>Tabla de referencia de códigos de países

En la tabla siguiente se muestran los valores del código de país para el parámetro-MediaRelayRoutingLocationOverride:

| Tercer         | Codifica 
|-----------------|--------------------|
| Afganistán     | Pulsa |
| Islas Åland   | AX150 |
| Albania         | AL |
| Argelia         | DZ |
| Samoa Americana  | CUYA |
| Andorra         | AD |
| Angola          | ACTIVACIÓN |
| Anguila        | EMPLEADOS |
| Antártida      | AQ | 
| Antigua y Barbuda | AG |
| Argentina       | AR |
| Armenia         | MEDIANOCHE |
| Aruba           | AW |
| Australia       | AU |
| Austria         | EN |
| Azerbaiyán      | Arizona |
| Bahamas         | BS |
| Baréin         | BH |
| Bangladesh      | BD |
| Barbados        | BB |
| Belarús         | BY |
| Bélgica         | BE |
| Belice          | BZ |
| Benín           | BJ |
| Bermudas         | BM |
| Bután          | BT |
| Bolivia         | CUADRO |
| Bonaire         | BQ |
| Bosnia y Herzegovina | BA |
| Botsuana        | CONSUMI |
| Isla Bouvet   | VN |
| Brasil          | BR |
| Territorio británico del océano Índico | E |
| Islas Vírgenes Británicas | VG |
| Brunéi          | BN |
| Bulgaria        | BG |
| Burkina Faso    | BF |
| Burundi         | BUSO |
| Cabo verde      | Visualiza |
| Camboya        | KH |
| Camerún        | CM |
| Canadá          | CA |
| Islas Caimán  | KY |
| República Centroafricana | Nº |
| Chad0            | TID |
| Chile           | CL |
| China           | CN |
| Isla Christmas | SERIE |
| Islas Cocos (Keeling) | CC |
| Colombia        | CO |
| Comoras         | 000 |
| Congo           | CG |
| Congo (RDC)     | CD |
| Islas Cook    | CK |
| Costa Rica      | Nº |
| Costa de Marfil   | ELEMENTO |
| Croacia         | RR. HH. |
| Cuba0            | CU |
| Curacao         | CW |
| Chipre          | CY |
| Checoia         | CZ |
| Dinamarca         | DK |
| Yibuti        | DJ |
| Dominica        | MENSAJES directos |
| República Dominicana | Este |
| Ecuador         | EC |
| Egipto           | EG |
| El Salvador     | VP |
| Guinea Ecuatorial | GQ |
| Eritrea         | ER |
| Estonia         | EE |
| Eswatini        | SZ |
| Etiopía        | PENINSULAR |
| Islas Malvinas | EXTERNA |
| Islas Feroe   | & |
| Fiyi            | FJ |
| Finlandia         | FI |
| Francia          | FR |
| Guayana Francesa   | GF |
| Polinesia Francesa | Rep |
| Territorios australes franceses | CE |
| Gabón           | GA |
| Gambia          | GM |
| Georgia         | MBIAR |
| Alemania         | DE |
| Ghana           | Vent |
| Gibraltar       | ATENUA |
| Grecia          | IVA |
| Groenlandia       | GL |
| Granada         | GD |
| Guadalupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | VV |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | GY |
| Haití           | ALTO |
| Islas Heard y McDonald | HM |
| Honduras        | HN |
| RAE de Hong Kong   | HK |
| Hungría         | HU |
| Islandia         | CONSISTE |
| India           | POR |
| Indonesia       | ID |
| Irán            | MANDO |
| Iraq            | IQ |
| Irlanda         | IE |
| Isla de Man     | MI |
| Israel          | IL |
| Italia           | QUE |
| Jamaica         | JM |
| Jan Mayen       | XJ |
| Japón           | JP |
| Jersey          | DIARIO |
| Jordania          | FE |
| Kazajstán      | KZ |
| Kenia           | KE |
| Kiribati        | KI |
| Corea           | KR |
| Kosovo          | KB |
| Kuwait          | TC |
| Kirguistán      | KG |
| Laos            | TAGALA |
| Letonia          | CICLE |
| Líbano         | LB |
| Lesoto         | EI |
| Liberia         | LR |
| Libia           | AL |
| Liechtenstein   | & |
| Lituania       | LT |
| Luxemburgo      | LU |
| RAE de Macao       | LUN |
| Madagascar      | MG |
| Malawi          | PM |
| Malasia        | MY |
| Maldivas        | MV |
| Malí            | LINGÜE |
| Malta           | MT |
| Islas Marshall | MH |
| Martinica      | MÁGICO |
| Mauritania      | Sr |
| Mauricio       | MU |
| Mayotte         | YT |
| México          | MX |
| Micronesia      | FM |
| Moldova         | MD |
| Mónaco          | MC |
| Mongolia        | MN |
| Montenegro      | Millenium |
| Montserrat      | Sra |
| Marruecos         | PROMEDIO |
| Mozambique      | MZ |
| Myanmar         | MM |
| Namibia         | NA |
| Nauru0           | Nº |
| Nepal           | NP |
| Países Bajos     | NL |
| Nueva Caledonia   | NC |
| Nueva Zelanda     | Zelanda |
| Nicaragua       | NI |
| Níger           | NE |
| Nigeria         | NG |
| Niue            | NY |
| Isla Norfolk  | NF |
| Corea del norte     | KGF |
| Macedonia del norte | MK |
| Islas Marianas del Norte | NP |
| Noruega          | No |
| Omán            | OM |
| Pakistán        | CLAVES |
| Palaos           | PAN |
| Autoridad Palestina | PCL |
| Panamá          | PA |
| Papúa Nueva Guinea | PG |
| Paraguay        | PY |
| Perú            | PE |
| Filipinas     | PH |
| Islas Pitcairn | VPN |
| Polonia          | PL |
| Portugal        | PT |
| Puerto Rico     | RR |
| Qatar           | QA |
| Reunión         | Volviendo |
| Rumanía         | RO |
| Rusia          | RU |
| Ruanda          | RW |
| Saba            | Prime |
| San Bartolomé | BL |
| San Cristóbal y Nieves | 5,0 |
| Santa Lucía     | ECX |
| San Martín    | M |
| San Pedro y Miquelón | Gerente |
| San Vicente y las Granadinas | CIRCUITO |
| Samoa           | EB |
| San Marino      | Gestor |
| Santo Tomé y Príncipe | San |
| Arabia Saudí    | SA |
| Senegal         | SN |
| Serbia          | RS |
| Seychelles      | SC |
| Sierra Leona    | SL | 
| Singapur       | SG |
| San Eustaquio  | CAMPO |
| Sint Maarten0    | SX |
| Eslovaquia        | SK |
| Eslovenia        | SL |
| Islas Salomón | ENSAMBLA |
| Somalia0         | PUES |
| Sudáfrica    | ZA |
| Georgia del Sur e islas Sandwich del sur | G |
| Sudán del sur     | SS |
| España           | ES |
| Sri Lanka       | LK |
| Santa Elena, ascensión, Tristán da Cunha | AP |
| Sudán           | DT |
| Surinam        | REVISIÓN |
| Svalbard        | SJ |
| Suecia          | SE |
| Suiza     | CH |
| Siria           | SY |
| Taiwán          | TW |
| Tayikistán      | TJ |
| Tanzania        | TZ |
| Tailandia        | TH |
| Timor Oriental     | TL |
| Togo            | TG |
| Tokelau1         | TK |
| Tonga0           | Para |
| Trinidad y Tobago | TT |
| Túnez         | TN |
| Turquía          | TR |
| Turkmenistán    | MT |
| Islas Turcas y Caicos | CT |
| Tuvalu1          | TELEVISIVO |
| Islas periféricas de los Estados Unidos | PUEDA |
| Islas Vírgenes de los Estados Unidos | VI |
| Uganda          | UG |
| Ucrania         | PAISAPAY |
| Emiratos Árabes Unidos | AE |
| Reino Unido  | GB |
| Estados Unidos   | DÉJEN |
| Uruguay         | UY |
| Uzbekistán      | UZ |
| Vanuatu0         | ACTIVADA |
| Ciudad del Vaticano    | 9.600 |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis y Futuna | WF |
| Yemen           | TAL |
| Zambia          | ZM |
| Zimbabue        | ZW |

