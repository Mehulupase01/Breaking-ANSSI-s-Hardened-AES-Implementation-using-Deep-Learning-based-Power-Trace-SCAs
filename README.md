# Breaking ANSSI's Hardened AES Implementation using Deep-Learning based Power-Trace SCAs
 This project evaluates the vulnerability of ANSSI’s masked AES to side-channel attacks (SCA) using deep learning models. It explores the effects of masking and shuffling countermeasures and utilizes Multi-Task Learning (MTL) to recover encryption keys from power traces effectively

# Breaking ANSSI's Hardened AES Implementation Using Machine Learning Based Side-Channel Attacks

This project evaluates the effectiveness of **ANSSI’s masked AES-128 bit implementation**, designed to protect against side-channel attacks, specifically focusing on the **affine masking** and **shuffling countermeasures**. Using **Machine Learning (ML) models**, we analyze how vulnerable this hardened implementation is to **side-channel attacks (SCAs)** and propose enhancements for more robust cryptographic defenses.

---

## **Project Overview**

This project investigates the **masked AES encryption** algorithm developed by **ANSSI** (French National Cybersecurity Agency) to withstand **Side-Channel Attacks (SCA)**. It focuses on the **affine masking** and **shuffling** countermeasures integrated into the AES implementation. The main objective is to assess how well these defenses hold up against modern **machine learning (ML)-driven SCAs**, particularly when using advanced techniques like **multi-task learning (MTL)**.

The **ASCADv2 dataset** was used for the experiments, which contains **power trace samples** from devices running ANSSI's AES implementation. We use **Deep Learning** models to perform SCAs, targeting intermediate values and recovering encryption keys by analyzing power traces.

---

## **File Structure**

- **`AES (Masked & Unmasked) + ML Model.ipynb`**: Implements the main **AES attack** using machine learning to perform **side-channel analysis**.
- **`Power Trace (ANSSI Masked).ipynb`**: Processes the **masked AES power traces** for attack.
- **`Power Trace (AT-MEGA Unmasked).ipynb`**: Works with **unmasked AES power traces** to perform SCAs.
- **`Unmasked.png`**: Shows the power trace for **unmasked AES** encryption.
- **`Masked.png`**: Displays the power trace for **masked AES** encryption.
- **`Crytpography Report.pdf`**: The **project report** detailing methodology, experiments, and results.
- **`How ANSSI Designed and Tested Their Masked AES.pdf`**: Research paper describing the **ANSSI implementation**.
  
---

## **Requirements**

To run the code and reproduce results, install the dependencies by running:

```bash
pip install -r requirements.txt
```

## **Running the Experiments**

The experiments can be re-executed by running the main .ipynb files. The model training and evaluation will proceed as per the specified parameters in each notebook. Additionally, you can run all experiments at once using the following script:

## Results and Evaluation

The key evaluation metrics used are:

- **Guessing Entropy (GE)**: The average rank position of the correct key among the possible guesses.
- **Success Rate**: The proportion of attacks that successfully recover the correct key within a given number of trials.

**Sample Results:**
1. **Unmasked AES**: The **Guessing Entropy** was high, typically around **30**.
2. **Masked AES with MTL**: After enhancing the model with **multi-task learning**, the **Guessing Entropy** dropped significantly to **under 5**, and the **success rate** improved to **over 80%**.

These results highlight the vulnerability of ANSSI’s hardened AES implementation to **deep learning-based SCAs**, suggesting the need for improved countermeasures.

## Conclusion

The project demonstrates that despite the use of **affine masking** and **shuffling**, the **ANSSI AES-128 implementation** can still be attacked effectively using **deep learning models**. The **Multi-Task Learning (MTL)** approach proved to be highly effective in targeting multiple computations simultaneously, significantly improving the success of the attack. These findings underline the importance of continuous improvement in cryptographic defenses, especially as machine learning and side-channel analysis techniques evolve.

## References

1. **ANSSI Masked AES Implementation**: [ANSSI AES GitHub Repository](https://github.com/ANSSI-FR/SecAESSTM32)
2. **Side-Channel Attacks (SCA) on AES**: Masure, L., Strullu, R. (2020). **Breaking ANSSI’s Hardened AES**. 
3. **Deep Learning for Side-Channel Attacks**: Maghrebi, H. (2020). **Multi-task learning for side-channel analysis**.
4. **ASCADv2 Dataset**: [ASCADv2 Dataset](https://www.data.gouv.fr/fr/datasets/ascadv2/)
5. **Research Paper on Masked AES**: [How ANSSI Designed and Tested Their Masked AES](https://www.researchgate.net/publication/343693537)
