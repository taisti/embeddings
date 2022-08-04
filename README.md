# The repository contains implementation of embedding training for ingredients substitutions

## BASELINE

The baseline embedding method is implemented according to simplified method presented in the Veganizer paper. It is based on computing FastText embeddings on pseudo-sentences constructed from lists of ingredients. Each recipe is converted into one pseudo-sentence containing all its ingredients without measure words. Multiple word ingredients are joined with "_" character. 

Baseline usage

- Copy the repository.
- Install the requirements of recommender repository plus the `fasttext` library.
- Download the dataset and extracte it to the project directory.
- Open the Jupyter notebook and follow the instructions. 

If you want to *use already trained model* (provided at Google Drive) you should directly skip to "Wczytanie modelu" section or simply use the code:
```
import fasttext
model = fasttext.load_model("MODEL_FILE.bin")
model.get_nearest_neighbors('INGREDIENT_WORD')
```

Additionally, the Jupyter notebook also exports embedding matrix to a file "embeddings.txt" (also provided at Google Drive)

## Recommendations for selected entities

```
chicken
(0.9290194511413574, 'citi_chicken')
(0.893699049949646, 'mix_chicken_piec')
(0.8879286646842957, 'chicken_halv')
(0.8790009021759033, 'chicken_portion')
(0.8712169528007507, 'broil_chicken')
(0.8696103692054749, 'chicken_chicken')
(0.867918074131012, 'chicken_cut')
(0.8649100661277771, 'chicken_ala_king')
(0.8585206866264343, 'meat_chicken')
(0.8568282723426819, 'veggi_chicken')

tofu
(0.9260441660881042, 'tofu_silken')
(0.8897832632064819, 'bake_tofu')
(0.8827080726623535, 'egg_tofu')
(0.8749420046806335, 'tofu_firm')
(0.870351254940033, 'silk_tofu')
(0.8676044940948486, 'silki_tofu')
(0.8665119409561157, 'tofu_skin')
(0.8615848422050476, 'silken_tofu_firm')
(0.8584445118904114, 'silken_tofu')
(0.8566809296607971, 'silken')

milk
(0.8302230834960938, 'evapor_milk')
(0.8208866119384766, 'butter')
(0.8154518008232117, 'egg')
(0.8121494650840759, 'milnot_cream')
(0.8046228885650635, 'milnot_milk')
(0.803139865398407, 'dairi_half_half')
(0.7996000647544861, 'evapor')
(0.7978138327598572, 'carnat_evapor_milk')
(0.79683518409729, 'margarin')
(0.7900131344795227, 'pet_evapor_milk')

egg
(0.8154520392417908, 'milk')
(0.8000625967979431, 'egg_unbeaten')
(0.7926957011222839, 'unbeaten_egg')
(0.7894937992095947, 'butter')
(0.7841209769248962, 'egg_oor')
(0.7738681435585022, 'salt')
(0.7649752497673035, '</s>')
(0.756428599357605, 'mik')
(0.7557492256164551, 'margain')
(0.7517643570899963, 'b_p')

banana
(0.902548611164093, 'dole_banana')
(0.8916700482368469, 'bananna')
(0.882179319858551, 'strawberri_banana_yogurt')
(0.8785958290100098, 'med_banana')
(0.8780544996261597, 'bannana')
(0.8745425939559937, 'strawberri_banana')
(0.8626872301101685, 'strawberri_banana_flavor')
(0.8623504638671875, 'overrip_banana')
(0.862296998500824, 'strawberri_banana_nectar')
(0.8590580821037292, 'rip_banana')

lentil
(0.9081096053123474, 'split_lentil')
(0.8812063336372375, 'masoor_lentil')
(0.8740416765213013, 'urad_lentil')
(0.8708998560905457, 'moong_lentil')
(0.865321695804596, 'du_puy_lentil')
(0.8652557730674744, 'mix_lentil')
(0.8622457385063171, 'lentil_bean')
(0.848703145980835, 'french_lentil')
(0.8473439812660217, 'brown_lentil')
(0.836576521396637, 'puy_lentil')

soy_cream
(0.8419979810714722, 'plain_soy_creamer')
(0.8305408358573914, 'soy_creamer')
(0.7835875153541565, 'soya_cream')
(0.7811110615730286, 'soya_milk')
(0.7789571285247803, 'soymilk')
(0.7722225785255432, 'plain_soy_milk')
(0.765313446521759, 'soy_cream_chees')
(0.7645689249038696, 'soy_margarin')
(0.7640460133552551, 'vegan_whip_cream')
(0.7640421986579895, 'cashew_cream')

butter
(0.8651416897773743, 'margarin')
(0.8280642032623291, 'magarin')
(0.8208865523338318, 'milk')
(0.8206565976142883, 'chiffon_margarin')
(0.8184331059455872, 'oleo_margarin')
(0.817577064037323, 'oleomargarin')
(0.8059778213500977, 'margain')
(0.8045403957366943, 'butter_margarin')
(0.7969185709953308, 'margarin_butter')
(0.7916005253791809, 'parkay_margarin')

gouda
(0.897088348865509, 'gouda_chees')
(0.8351644277572632, 'emmental_chees')
(0.8341633081436157, 'emment_chees')
(0.8328235149383545, 'gruyer_chees')
(0.8323578834533691, 'comt_chees')
(0.8284788727760315, 'gruyr_chees')
(0.8284211158752441, 'st_andr_chees')
(0.8273360729217529, 'gruyer')
(0.8250493407249451, 'mimolett_chees')
(0.8190907835960388, 'emmenth_chees')
```
