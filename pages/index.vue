<template>
  <div>
    <accordion-list 
    v-for="item in accordionData"
    :items="item"
    :key="item.title" />
  </div>
</template>

<script>
  import AccordionList from "../components/accordion-list/accordion-list";

  export default {
    components: { AccordionList },
    data() {
      return {
        accordionData: [
          {
            title: "Accordion 1",
            sections: [
              {
                slug: "et-hi-quidem-ita-non-sola-virtute-finem",
                title: "Et hi quidem ita non sola virtute finem?",
                body:
                  "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href=\"http://loripsum.net/\" target=\"_blank\">Ubi ut eam caperet aut quando?</a> <i>Haec igitur Epicuri non probo, inquam.</i> Scisse enim te quis coarguere possit? Hoc sic expositum dissimile est superiori. <b>Mihi enim satis est, ipsis non satis.</b> Nam adhuc, meo fortasse vitio, quid ego quaeram non perspicis.<p>"
              },
              {
                slug: "lorem-ipsum-dolor-sit-amet",
                title: "Lorem ipsum dolor sit amet?",
                body:
                  "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Theophrastus mediocriterne delectat, cum tractat locos ab Aristotele ante tractatos? Cur igitur, cum de re conveniat, non malumus usitate loqui? Praeterea sublata cognitione et scientia tollitur omnis ratio et vitae degendae et rerum gerendarum. Collatio igitur ista te nihil iuvat. Verum hoc idem saepe faciamus. Itaque dicunt nec dubitant: mihi sic usus est, tibi ut opus est facto, fac. </p>"
              },
              {
                slug: "sint-modo-partes-vitae-beatae",
                title: "Sint modo partes vitae beatae?",
                body:
                  "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. <b>Sint modo partes vitae beatae.</b> Hoc mihi cum tuo fratre convenit. Varietates autem iniurasque fortunae facile veteres philosophorum praeceptis instituta vita superabat. Theophrasti igitur, inquit, tibi liber ille placet de beata vita? Ita enim vivunt quidam, ut eorum vita refellatur oratio. <a href=\"http://loripsum.net/\" target=\"_blank\">Si longus, levis dictata sunt.</a> </p><ul><li>Intrandum est igitur in rerum naturam et penitus quid ea postulet pervidendum;</li><li>Minime vero, inquit ille, consentit.</li><li>Duo Reges: constructio interrete.</li></ul>"
              }
            ]
          },
          {
            title: "Accordion 2",
            sections: [
              {
                slug: "platonis-illi-et-deinceps-qui-eorum-auditores-fuerunt",
                title: "Platonis illi et deinceps qui eorum auditores fuerunt?",
                body:
                  '<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vitae autem degendae ratio maxime quidem illis placuit quieta. Suam denique cuique naturam esse ad vivendum ducem. <a href="http://loripsum.net/" target="_blank">Mihi enim satis est, ipsis non satis.</a> Quid, si reviviscant Platonis illi et deinceps qui eorum auditores fuerunt, et tecum ita loquantur? <p><p><b>Cave putes quicquam esse verius.</b> <i>Non laboro, inquit, de nomine.</i> Negat enim summo bono afferre incrementum diem. Vide igitur ne non debeas verbis nostris uti, sententiis tuis. <i>Scrupulum, inquam, abeunti;</i> <a href="http://loripsum.net/" target="_blank">Ratio quidem vestra sic cogit.</a> </p><p><b>Tu vero, inquam, ducas licet, si sequetur;</b> Est autem officium, quod ita factum est, ut eius facti probabilis ratio reddi possit. <i>Tum Triarius: Posthac quidem, inquit, audacius.</i> Duo Reges: constructio interrete. <b>Non igitur bene.</b> <a href="http://loripsum.net/" target="_blank">Faceres tu quidem, Torquate, haec omnia;</a> </p>'
              },
              {
                slug: "fortitudinis-quaedam-praecepta-sunt-ac-paene-leges",
                title: "Fortitudinis quaedam praecepta sunt ac paene leges?",
                body:
                  "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quicquid enim a sapientia proficiscitur, id continuo debet expletum esse omnibus suis partibus; Quid, de quo nulla dissensio est? Ergo in gubernando nihil, in officio plurimum interest, quo in genere peccetur. Hoc dixerit potius Ennius: Nimium boni est, cui nihil est mali. <mark>Istic sum, inquit.</mark> Ergo instituto veterum, quo etiam Stoici utuntur, hinc capiamus exordium. Duo Reges: constructio interrete. Sed quid attinet de rebus tam apertis plura requirere? Sed mehercule pergrata mihi oratio tua. Expressa vero in iis aetatibus, quae iam confirmatae sunt. </p><p>Fortitudinis quaedam praecepta sunt ac paene leges, quae effeminari virum vetant in dolore. Primum in nostrane potestate est, quid meminerimus? Quid censes in Latino fore? Causa autem fuit huc veniendi ut quosdam hinc libros promerem. Propter nos enim illam, non propter eam nosmet ipsos diligimus. </p>"
              },
              {
                slug: "voluptas-percipitur-ex-vilissimis-rebus-quam",
                title: "Voluptas percipitur ex vilissimis rebus quam?",
                body:
                  "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Idem iste, inquam, de voluptate quid sentit? Tu vero, inquam, ducas licet, si sequetur; Tum Triarius: Posthac quidem, inquit, audacius. Unum nescio, quo modo possit, si luxuriosus sit, finitas cupiditates habere. </p><p>Me igitur ipsum ames oportet, non mea, si veri amici futuri sumus. Non minor, inquit, voluptas percipitur ex vilissimis rebus quam ex pretiosissimis.</p>"
              },
              {
                slug: "theophrastum-tamen-adhibeamus-ad-pleraque",
                title: "Theophrastum tamen adhibeamus ad pleraque?",
                body:
                  "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Non modo carum sibi quemque, verum etiam vehementer carum esse? Duo Reges: constructio interrete. <b>Proclivi currit oratio.</b> Theophrastum tamen adhibeamus ad pleraque, dum modo plus in virtute teneamus, quam ille tenuit, firmitatis et roboris. Non autem hoc: igitur ne illud quidem. Tuo vero id quidem, inquam, arbitratu. In quibus doctissimi illi veteres inesse quiddam caeleste et divinum putaverunt. <b>Easdemne res?</b> </p>"
              }
            ]
          }
        ]
      }
    }
  }
</script>
