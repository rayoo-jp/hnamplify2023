import { ChangeEvent, Dispatch } from "vue";
import { LanguageOptionGroup } from "../data/language-options";

type Props = {
  optionGroups: LanguageOptionGroup[];
  defaultValue: string;
<string>;
};

export const SelectBox = ({
  optionGroups,
  defaultValue,
  setSelectOption,
}: Props) => {
  const handleChange = (event: ChangeEvent<HTMLSelectElement>) => {
    setSelectOption(event.target.value);
  };

  return (
    <select onChange={handleChange} defaultValue={defaultValue}>
      {optionGroups.map((optionGroups) => {
        return (
          <optgroup key={optionGroups.group} label={optionGroups.group}>
            {optionGroups.options.map((option) => {
              return (
                <option key={option.value} value={option.value}>
                  {option.label}
                </option>
              );
            })}
          </optgroup>
        );
      })}
    </select>
  );
};