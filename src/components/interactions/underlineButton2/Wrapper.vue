<template>
  <StyledWrapper>
    <StyledButtonWrapper>
      <Button1 class="button">Center</Button1>
    </StyledButtonWrapper>
    <StyledButtonWrapper>
      <Button2 class="button">Left</Button2>
    </StyledButtonWrapper>
    <StyledButtonWrapper>
      <Button3 class="button">Bottom</Button3>
    </StyledButtonWrapper>
  </StyledWrapper>
</template>

<script>
import styled from "vue-styled-components";
import { rgba } from "polished";

const transitionDuration = "0.45s";

const StyledWrapper = styled.div``;

const StyledButtonWrapper = styled.div`
  margin-bottom: 1.75rem;
`;

const StyledButton = styled.button`
  position: relative;
  overflow: hidden;
  width: 200px;
  height: 50px;
  background: #ffebf1;
  color: ${rgba("#090C22", 0.85)};
  font-size: 18px;
  font-weight: 600;

  &:hover::after {
    transform: scale(1);
  }

  &::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 3px;
    background: #f90549;
    transition: transform ${transitionDuration};
  }
`;

const Button1 = styled(StyledButton)`
  &.button:hover::after {
    transform: scale(1, 1);
  }

  &.button::after {
    transform: scale(0, 1);
    transform-origin: 50% 0%;
  }
`;

const Button2 = styled(StyledButton)`
  &.button:hover::after {
    transform: scale(1, 1);
  }

  &.button::after {
    transform: scale(0, 1);
    transform-origin: 0% 100%;
  }
`;

const Button3 = styled(StyledButton)`
  &.button:hover::after {
    transform: scale(1, 1);
  }

  &.button::after {
    transform: scale(1, 1) translateY(3px);
  }
`;

export default {
  components: {
    StyledWrapper,
    StyledButtonWrapper,
    Button1,
    Button2,
    Button3
  }
};
</script>
