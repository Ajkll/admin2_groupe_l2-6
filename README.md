# admin2_groupe_l2-6

2.2. Validation de la clé publique via la zone parente

Pour garantir la validité de la clé publique, il faut, comme déjà mentionné plus haut, utiliser une chaîne de confiance. Le DNSSEC se base sur la structure hiérarchique du DNS pour cela : la racine du DNS sera la racine de la chaîne de confiance. La racine se portera garante des TLDs en fournissant une signature validant leurs clés publiques dans un RR de type DS. Les TLDs, quant à eux, contiendront, dans leur fichier de zone, des records DS pour leurs sous-domaines, et ainsi de suite.

Dans le cadre de votre projet, vous devez donc fournir un RR DS à votre domaine parent.

Pour obtenir un resource-record DS au départ de la clé DNSSEC publique, Bind propose l’outil dnssec-dsfromkey. Pour l’utiliser, identifier le fichier de clé KSK dans votre répertoire de travail Bind, et donnez-le en paramètre à l’outil.

Ensuite, vous devriez normalement transmettre ce record à votre zone parente, en l’occurrence ephec-ti.be, gérée par les professeur. Malheureusement, le fournisseur de nom de domaine ne donne pas la possibilité d’ajouter un DS dans la zone. Nous vous demandons donc simplement d’indiquer ce DS record dans votre page Wiki Github dédiée à votre configuration DNS.


; le resultat attendue:"ex" .
