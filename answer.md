 1 . <?php
    function getDigitsArray($number)
    {
        $numberStr = (string) $number;
        $digitsArray = str_split($numberStr);
        $digitsArray = array_map('intval', $digitsArray);
        return $digitsArray;
    }
    $number = 12345;
    $digitsArray = getDigitsArray($number);
        print_r($digitsArray);
    ?>


2.<?php
  function translateToPigLatin($text)
  {
      $words = explode(' ', $text);
      $pigLatinWords = [];

      foreach ($words as $word) {
          $firstLetter = strtolower(substr($word, 0, 1));
          $remainingLetters = substr($word, 1);
          $pigLatinWord = $remainingLetters . $firstLetter . 'ay';
          $pigLatinWords[] = $pigLatinWord;
      }

      return implode(' ', $pigLatinWords);
  }

  function translateFromPigLatin($text)
  {
      $words = explode(' ', $text);
      $enghWords = [];

      foreach ($words as $word) {
          $lastTwoLetters = strtolower(substr($word, -3, 2));
          $remainingLetters = substr($word, 0, -3);
          $enghWord = $lastTwoLetters . $remainingLetters;
          $engWords[] = $englishWord;
      }

      return implode(' ', $engWords);
  }
  $text = "Join with yellowfish";
  $pigLatin = translateToPigLatin($text);

  echo  $pigLatin,"\n";
  ?>


 3. <?php
        function rotateArray(&$array, $k)
    {
        $length = count($array);
        $k = $k % $length;
        reverseArray($array, 0, $length - 1);
        reverseArray($array, 0, $k - 1);
        reverseArray($array, $k, $length - 1);
    }
    function reverseArray(&$array, $start, $end)
    {
        while ($start < $end) {
            $temp = $array[$start];
            $array[$start] = $array[$end];
            $array[$end] = $temp;
            $start++;
            $end--;
        }
    }
    $array = [1, 2, 3, 4, 5, 6];
    $k = 2;
    rotateArray($array, $k);
    print_r($array);
    ?>